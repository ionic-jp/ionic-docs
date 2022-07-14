---
title: "ion-alert"
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

import Props from '@site/static/auto-generated/alert/props.md';
import Events from '@site/static/auto-generated/alert/events.md';
import Methods from '@site/static/auto-generated/alert/methods.md';
import Parts from '@site/static/auto-generated/alert/parts.md';
import CustomProps from '@site/static/auto-generated/alert/custom-props.md';
import Slots from '@site/static/auto-generated/alert/slots.md';

<head>
  <title>ion-alert: Ionic API Alert Buttons with Custom Message Prompts</title>
  <meta name="description" content="ion-alert dialog presents or collects information using inputs. Custom alert button messages appear above the app's content and must be manually dismissed." />
</head>

import EncapsulationPill from '@components/page/api/EncapsulationPill';
import APITOCInline from '@components/page/api/APITOCInline';

<EncapsulationPill type="scoped" />



Alertは、ユーザーに情報を提示したり、Inputを使用してユーザーから情報を収集したりするダイアログです。Alertはアプリのコンテンツの上に表示され、アプリの利用を再開する前にユーザーが手動で破棄する必要があります。 オプションに `header`, `subHeader` と `message` を持つことができます。

## Presenting

### Controller

import Controller from '@site/static/usage/alert/presenting/controller/index.md';

<Controller />

### Inline

When using Ionic with React or Vue, `ion-alert` can also be placed directly in the template through use of the `isOpen` property. Note that `isOpen` must be set to `false` manually when the alert is dismissed; it will not be updated automatically.

<Tabs defaultValue="react" values={[{ value: 'react', label: 'React' }, { value: 'vue', label: 'Vue' }]}>
<TabItem value="react">

```tsx
import React, { useState } from 'react';
import { IonAlert, IonButton, IonContent } from '@ionic/react';

function Example() {
  const [showAlert, setShowAlert] = useState(false);

  return (
    <IonContent>
      <IonButton onClick={() => setShowAlert(true)}>Click Me</IonButton>
      <IonAlert
        isOpen={showAlert}
        onDidDismiss={() => setShowAlert(false)}
        header="Alert"
        subHeader="Important message"
        message="This is an alert!"
        buttons={['OK']}
      />
    </IonContent>
  );
}
```

</TabItem>
<TabItem value="vue">

```html
<template>
  <ion-content>
    <ion-button @click="setOpen(true)">Show Alert</ion-button>
    <ion-alert
      :is-open="isOpenRef"
      header="Alert"
      sub-header="Important message"
      message="This is an alert!"
      :buttons="['OK']"
      @didDismiss="setOpen(false)"
    ></ion-alert>
  </ion-content>
</template>

<script lang="ts">
import { IonAlert, IonButton, IonContent } from '@ionic/vue';
import { defineComponent, ref } from 'vue';

export default defineComponent({
  components: { IonAlert, IonButton },
  setup() {
    const isOpenRef = ref(false);
    const setOpen = (state: boolean) => isOpenRef.value = state;
    
    return { isOpenRef, setOpen }
  }
});
</script>
```

</TabItem>
</Tabs>

## Buttons

`buttons` の配列には、各buttonの `text` のプロパティと、オプションで `handler` を利用することができます。 `handler` が `false` を返した場合、buttonがクリックされてもAlertは自動的に解除されません。すべての `buttons` は、左から右にボタン配列に追加された順序で表示されます。 Note: 一番右のボタン(配列の最後の1つ)がメインボタンです。

オプションで、`cancel`のような `role` プロパティをボタンに追加することができます。もし `cancel` ロールがボタンのいずれかに設定されている場合、バックドロップをタップしてアラートが解除されると、キャンセルロールを持つボタンから handler が起動されます。

import Buttons from '@site/static/usage/alert/buttons/index.md';

<Buttons />


## Inputs

Alertには、複数の異なるInputを含めることもでき、そのデータをアプリで受け取ることができます。 Inputはユーザーに情報の入力を促す簡単な方法として使用できます。Radios, checkboxes と text inputs textarea はすべて利用できますが、これらを混ぜて利用することはできません。例えば、Alertはすべてbutton Inputであったり、すべてcheckboxでのInputを持つことはできますが、同一のAlertにradioとcheckbox Inputを混ぜることはできません。ただし、"text" Inputでは、 `url`, `email`, `text` などの複数のtypeを混ぜて利用することはできます。 Alertのガイドラインに収まらない複雑なForm UIが必要な場合は、代わりにModal内でFormを構築することをお勧めします。

### Text Inputs Example

import TextInputs from '@site/static/usage/alert/inputs/text-inputs/index.md';

<TextInputs />

### Radio Example

import Radios from '@site/static/usage/alert/inputs/radios/index.md';

<Radios />

## Customization

Alert uses scoped encapsulation, which means it will automatically scope its CSS by appending each of the styles with an additional class at runtime. Overriding scoped selectors in CSS requires a [higher specificity](https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity) selector.

We recommend passing a custom class to `cssClass` in the `create` method and using that to add custom styles to the host and inner elements. This property can also accept multiple classes separated by spaces.

```css
/* DOES NOT WORK - not specific enough */
.alert-wrapper {
  background: #e5e5e5;
}

/* Works - pass "my-custom-class" in cssClass to increase specificity */
.my-custom-class .alert-wrapper {
  background: #e5e5e5;
}
```

Any of the defined [CSS Custom Properties](#css-custom-properties) can be used to style the Alert without needing to target individual elements:

```css
.my-custom-class {
  --background: #e5e5e5;
}
```

import Customization from '@site/static/usage/alert/customization/index.md';

<Customization />

:::note
 If you are building an Ionic Angular app, the styles need to be added to a global stylesheet file.
:::


## Interfaces

### AlertButton

```typescript
interface AlertButton {
  text: string;
  role?: 'cancel' | 'destructive' | string;
  cssClass?: string | string[];
  handler?: (value: any) => boolean | void | {[key: string]: any};
}
```


### AlertInput

```typescript
interface AlertInput {
  type?: TextFieldTypes | 'checkbox' | 'radio' | 'textarea';
  name?: string;
  placeholder?: string;
  value?: any;
  label?: string;
  checked?: boolean;
  disabled?: boolean;
  id?: string;
  handler?: (input: AlertInput) => void;
  min?: string | number;
  max?: string | number;
  cssClass?: string | string[];
  attributes?: { [key: string]: any };
  tabindex?: number;
}
```


### AlertOptions

```typescript
interface AlertOptions {
  header?: string;
  subHeader?: string;
  message?: string | IonicSafeString;
  cssClass?: string | string[];
  inputs?: AlertInput[];
  buttons?: (AlertButton | string)[];
  backdropDismiss?: boolean;
  translucent?: boolean;
  animated?: boolean;
  htmlAttributes?: { [key: string]: any };

  mode?: Mode;
  keyboardClose?: boolean;
  id?: string;

  enterAnimation?: AnimationBuilder;
  leaveAnimation?: AnimationBuilder;
}
```

## Properties
<Props />

## Events
<Events />

## Methods
<Methods />

## CSS Shadow Parts
<Parts />

## CSS Custom Properties
<CustomProps />

## Slots
<Slots />