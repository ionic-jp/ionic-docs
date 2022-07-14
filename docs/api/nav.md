---
title: "ion-nav"
hide_table_of_contents: true
demoUrl: "/docs/demos/api/nav/index.html"
demoSourceUrl: "https://github.com/ionic-team/ionic-docs/tree/main/static/demos/api/nav/index.html"
---
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

import Props from '@site/static/auto-generated/nav/props.md';
import Events from '@site/static/auto-generated/nav/events.md';
import Methods from '@site/static/auto-generated/nav/methods.md';
import Parts from '@site/static/auto-generated/nav/parts.md';
import CustomProps from '@site/static/auto-generated/nav/custom-props.md';
import Slots from '@site/static/auto-generated/nav/slots.md';

<head>
  <title>ion-nav | Nav View Component for Ionic Framework Apps</title>
  <meta name="description" content="ion-nav is a standalone for loading arbitrary, and pushing new, components on to the stack. Loading Nav view, and pushing others, won't affect overall routers." />
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



Navは、任意のコンポーネントをロードし、スタックに新しいコンポーネントを追加するためのスタンドアロンコンポーネントです

RouterOutletとは異なり、Navは特定のルーターに関連付けられていません。つまり、Navコンポーネントをロードして他のコンポーネントをスタックに追加しても、ルーター全体のアプリケーションには影響しません。これは、独自のサブナビゲーションを必要とするが、アプリのURLに縛られないモーダルを持つことができるユースケースに適しています。

## Interfaces

### NavCustomEvent

While not required, this interface can be used in place of the `CustomEvent` interface for stronger typing with Ionic events emitted from this component.

```typescript
interface NavCustomEvent extends CustomEvent {
  target: HTMLIonNavElement;
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