---
sidebar_label: パフォーマンス
title: React パフォーマンス
---

<head>
  <title>React Performance Testing - Using Loops with Ionic App Components</title>
  <meta
    name="description"
    content="React performance testing for Ionic apps. When using loops with Ionic components, we recommend using React's key attribute. Read to learn more."
  />
</head>

## Loops with Ionic Components

When using loops with Ionic components, we recommend using React's `key` attribute. This allows React to re-render loop elements in an efficient way by only updating the content inside of the component rather than re-creating the component altogether.

By using `key` you can provide a stable identity for each loop element so React can track insertions and deletions within the iterator. Below is an example of how to use `key`:

**MyComponent.tsx**

```tsx
import React, { useState } from 'react';
import { IonContent, IonItem, IonLabel, IonPage } from '@ionic/react';

export const MyComponent: React.FC = () => {
  const [items, setItems] = useState([{ id: 0, value: 'Item 0' }, { id: 1, value: 'Item 1' }, ...]);

  return (
    <IonPage>
      <IonContent>
        {items.map(item => {
          return (
            <IonItem key={item.id}>
              <IonLabel>{item.value}</IonLabel>
            </IonItem>
          )
        })}
      </IonContent>
    </IonPage>
  )
}
```

In this example, we have an array of objects called `items`. Each object contains a `value` and an `id`. Using the `key` attribute, we pass the `item.id` for each object. This `id` is used to provide a stable identity for each loop element.

For more information on how React renders lists using `key` see: https://react.dev/learn/rendering-lists#keeping-list-items-in-order-with-key
