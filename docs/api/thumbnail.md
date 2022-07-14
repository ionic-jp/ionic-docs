---
title: "ion-thumbnail"
hide_table_of_contents: true
demoUrl: "/docs/demos/api/thumbnail/index.html"
demoSourceUrl: "https://github.com/ionic-team/ionic-docs/tree/main/static/demos/api/thumbnail/index.html"
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

import Props from '@site/static/auto-generated/thumbnail/props.md';
import Events from '@site/static/auto-generated/thumbnail/events.md';
import Methods from '@site/static/auto-generated/thumbnail/methods.md';
import Parts from '@site/static/auto-generated/thumbnail/parts.md';
import CustomProps from '@site/static/auto-generated/thumbnail/custom-props.md';
import Slots from '@site/static/auto-generated/thumbnail/slots.md';

<head>
  <title>ion-thumbnail | Thumbnail App Component to Wrap Images or Icons</title>
  <meta name="description" content="What is a thumbnail image? Thumbnail app components wrap an image or icon and can be used to display a layout of images or for previews of full-size images." />
</head>

import EncapsulationPill from '@components/page/api/EncapsulationPill';
import APITOCInline from '@components/page/api/APITOCInline';

<EncapsulationPill type="shadow" />

<h2 className="table-of-contents__title">Contents</h2>

<APITOCInline
  toc={toc}
  maxHeadingLevel={2}
  autogenerated={[Props, Events, Methods, Parts, CustomProps, Slots]}
/>



Thumbnailsは、通常、画像またはアイコンをラップする四角形のコンポーネントです。これを使用すると、大きな画像のグループを簡単に表示したり、フルサイズのイメージのプレビューを表示したりできます。

Thumbnailsは、単独で使用することも、任意の要素の内部で使用することもできます。`ion-item` の内部に配置すると、Thumbnailsのサイズが親コンポーネントに合わせて変更されます。Thumbnailsをアイテムの左側または右側に配置するには、slotをそれぞれ `start` または `end` に設定します。




## Usage

<Tabs groupId="framework" defaultValue="angular" values={[{ value: 'angular', label: 'Angular' }, { value: 'javascript', label: 'Javascript' }, { value: 'react', label: 'React' }, { value: 'stencil', label: 'Stencil' }, { value: 'vue', label: 'Vue' }]}>

<TabItem value="angular">

```html
<ion-thumbnail>
  <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y">
</ion-thumbnail>

<ion-item>
  <ion-thumbnail slot="start">
    <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y">
  </ion-thumbnail>
  <ion-label>Item Thumbnail</ion-label>
</ion-item>
```

</TabItem>


<TabItem value="javascript">

```html
<ion-thumbnail>
  <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y">
</ion-thumbnail>

<ion-item>
  <ion-thumbnail slot="start">
    <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y">
  </ion-thumbnail>
  <ion-label>Item Thumbnail</ion-label>
</ion-item>
```

</TabItem>


<TabItem value="react">

```tsx
import React from 'react';
import { IonThumbnail, IonItem, IonLabel, IonContent } from '@ionic/react';

export const ThumbnailExample: React.FC = () => (
  <IonContent>
    <IonThumbnail>
      <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y" />
    </IonThumbnail>

    <IonItem>
      <IonThumbnail slot="start">
        <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y" />
      </IonThumbnail>
      <IonLabel>Item Thumbnail</IonLabel>
    </IonItem>
  </IonContent>
);
```


</TabItem>


<TabItem value="stencil">

```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'thumbnail-example',
  styleUrl: 'thumbnail-example.css'
})
export class ThumbnailExample {
  render() {
    return [
      <ion-thumbnail>
        <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y"/>
      </ion-thumbnail>,

      <ion-item>
        <ion-thumbnail slot="start">
          <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y"/>
        </ion-thumbnail>
        <ion-label>Item Thumbnail</ion-label>
      </ion-item>
    ];
  }
}
```


</TabItem>


<TabItem value="vue">

```html
<template>
  <ion-thumbnail>
    <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y">
  </ion-thumbnail>

  <ion-item>
    <ion-thumbnail slot="start">
      <img src="https://gravatar.com/avatar/dba6bae8c566f9d4041fb9cd9ada7741?d=identicon&f=y">
    </ion-thumbnail>
    <ion-label>Item Thumbnail</ion-label>
  </ion-item>
</template>

<script>
import { IonItem, IonLabel, IonThumbnail } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { IonItem, IonLabel, IonThumbnail }
});
</script>
```

</TabItem>

</Tabs>

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