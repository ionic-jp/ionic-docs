---
title: "ion-spinner"
hide_table_of_contents: true
demoUrl: "/docs/demos/api/spinner/index.html"
demoSourceUrl: "https://github.com/ionic-team/ionic-docs/tree/main/static/demos/api/spinner/index.html"
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

import Props from '@site/static/auto-generated/spinner/props.md';
import Events from '@site/static/auto-generated/spinner/events.md';
import Methods from '@site/static/auto-generated/spinner/methods.md';
import Parts from '@site/static/auto-generated/spinner/parts.md';
import CustomProps from '@site/static/auto-generated/spinner/custom-props.md';
import Slots from '@site/static/auto-generated/spinner/slots.md';

<head>
  <title>ion-spinner | Animated Spinner Icon Components and Properties</title>
  <meta name="description" content="The ion-spinner component provides a variety of animated SVG spinners. These icons indicate that the app is loading or performing another process to wait on." />
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



Spinnerコンポーネントには、さまざまなアニメーションつきのSVG Spinnerが用意されています。Spinnerは、アプリがコンテンツを読み込んだり、ユーザーが待つ必要のある別のプロセスを実行していることを視覚的に示すものです。

デフォルトのSpinnerはプラットフォームに基づいて使用されます。`ios`のデフォルトのSpinnerは`"lines"`であり、`android`のデフォルトは`"crescent"`である。プラットフォームが `ios` または `android` でない場合、Spinnerはデフォルトで `crescent` に設定されます。`name` プロパティが設定されている場合、プラットフォーム固有のSpinnerの代わりに指定されたSpinnerが使用されます。





## Usage

<Tabs groupId="framework" defaultValue="angular" values={[{ value: 'angular', label: 'Angular' }, { value: 'javascript', label: 'Javascript' }, { value: 'react', label: 'React' }, { value: 'stencil', label: 'Stencil' }, { value: 'vue', label: 'Vue' }]}>

<TabItem value="angular">

```html
<!-- Default Spinner -->
<ion-spinner></ion-spinner>

<!-- Lines -->
<ion-spinner name="lines"></ion-spinner>

<!-- Lines Small -->
<ion-spinner name="lines-small"></ion-spinner>

<!-- Dots -->
<ion-spinner name="dots"></ion-spinner>

<!-- Bubbles -->
<ion-spinner name="bubbles"></ion-spinner>

<!-- Circles -->
<ion-spinner name="circles"></ion-spinner>

<!-- Crescent -->
<ion-spinner name="crescent"></ion-spinner>

<!-- Paused Default Spinner -->
<ion-spinner paused></ion-spinner>
```


</TabItem>


<TabItem value="javascript">

```html
<!-- Default Spinner -->
<ion-spinner></ion-spinner>

<!-- Lines -->
<ion-spinner name="lines"></ion-spinner>

<!-- Lines Small -->
<ion-spinner name="lines-small"></ion-spinner>

<!-- Dots -->
<ion-spinner name="dots"></ion-spinner>

<!-- Bubbles -->
<ion-spinner name="bubbles"></ion-spinner>

<!-- Circles -->
<ion-spinner name="circles"></ion-spinner>

<!-- Crescent -->
<ion-spinner name="crescent"></ion-spinner>

<!-- Paused Default Spinner -->
<ion-spinner paused></ion-spinner>
```


</TabItem>


<TabItem value="react">

```tsx
import React from 'react';
import { IonSpinner, IonContent } from '@ionic/react';

export const SpinnerExample: React.FC = () => (
  <IonContent>
    {/*-- Default Spinner --*/}
    <IonSpinner />

    {/*-- Lines --*/}
    <IonSpinner name="lines" />

    {/*-- Lines Small --*/}
    <IonSpinner name="lines-small" />

    {/*-- Dots --*/}
    <IonSpinner name="dots" />

    {/*-- Bubbles --*/}
    <IonSpinner name="bubbles" />

    {/*-- Circles --*/}
    <IonSpinner name="circles" />

    {/*-- Crescent --*/}
    <IonSpinner name="crescent" />

    {/*-- Paused Default Spinner --*/}
    <IonSpinner paused />
  </IonContent>
);
```


</TabItem>


<TabItem value="stencil">

```tsx
import { Component, h } from '@stencil/core';

@Component({
  tag: 'spinner-example',
  styleUrl: 'spinner-example.css'
})
export class SpinnerExample {
  render() {
    return [
      // Default Spinner
      <ion-spinner></ion-spinner>,

      // Lines
      <ion-spinner name="lines"></ion-spinner>,

      // Lines Small
      <ion-spinner name="lines-small"></ion-spinner>,

      // Dots
      <ion-spinner name="dots"></ion-spinner>,

      // Bubbles
      <ion-spinner name="bubbles"></ion-spinner>,

      // Circles
      <ion-spinner name="circles"></ion-spinner>,

      // Crescent
      <ion-spinner name="crescent"></ion-spinner>,

      // Paused Default Spinner
      <ion-spinner paused={true}></ion-spinner>
    ];
  }
}
```


</TabItem>


<TabItem value="vue">

```html
<template>
  <!-- Default Spinner -->
  <ion-spinner></ion-spinner>

  <!-- Lines -->
  <ion-spinner name="lines"></ion-spinner>

  <!-- Lines Small -->
  <ion-spinner name="lines-small"></ion-spinner>

  <!-- Dots -->
  <ion-spinner name="dots"></ion-spinner>

  <!-- Bubbles -->
  <ion-spinner name="bubbles"></ion-spinner>

  <!-- Circles -->
  <ion-spinner name="circles"></ion-spinner>

  <!-- Crescent -->
  <ion-spinner name="crescent"></ion-spinner>

  <!-- Paused Default Spinner -->
  <ion-spinner paused></ion-spinner>
</template>

<script>
import { IonSpinner } from '@ionic/vue';
import { defineComponent } from 'vue';

export default defineComponent({
  components: { IonSpinner }
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