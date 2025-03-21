---
title: "ion-select"
---
import Props from '@ionic-internal/component-api/v8/select/props.md';
import Events from '@ionic-internal/component-api/v8/select/events.md';
import Methods from '@ionic-internal/component-api/v8/select/methods.md';
import Parts from '@ionic-internal/component-api/v8/select/parts.md';
import CustomProps from '@ionic-internal/component-api/v8/select/custom-props.mdx';
import Slots from '@ionic-internal/component-api/v8/select/slots.md';

<head>
  <title>ion-select: Select One or Multiple Value Boxes or Placeholders</title>
  <meta name="description" content="ion-selectは、選択された値（複数可）、またはプレースホルダー、ドロップダウンのアイコンによって表現されます。 selectをタップすると、選択しやすいリストを表示するダイアログボックスが表示されます。" />
</head>

import EncapsulationPill from '@components/page/api/EncapsulationPill';

<EncapsulationPill type="shadow" />


セレクトは、一連のオプションから1つまたは複数のオプションを選択するためのフォームコントロールです。ユーザーがセレクトをタップすると、ダイアログが表示され、すべてのオプションが大きく選択しやすいリストに表示されます。

selectは、子要素 `<ion-select-option>` とともに使用する必要があります。子要素のオプションに`value`属性が指定されていない場合、そのtextが値として使用されます。

`value` が `<ion-select>` にセットされている場合、オプションはその値に基づいて選択済みになります。

## Labels

ラベルは、Selectを説明するために使用します。これらは視覚的に使用することができ、また、ユーザーがSelectにフォーカスしているときには、スクリーンリーダーによって読み上げられます。これにより、ユーザーはSelectの意図を理解しやすくなります。セレクトには、ラベルを割り当てるいくつかの方法があります：

セレクトには、コンポーネントにラベルを指定するためのいくつかのオプションがあります：

- `label`プロパティ：プレーンテキストのラベルに使用します。
- `label`スロット：カスタム HTML ラベルに使用する。
- `aria-label`：スクリーンリーダー用のラベルとして使用されるが、ラベルは表示されない。

### Label Placement

ラベルはデフォルトではコンテンツの幅を占めます。開発者は `labelPlacement` プロパティを使用して、コントロールに対するラベルの配置を制御することができます。ここでは `label` プロパティを使用しているが、`labelPlacement` は `label` スロットと一緒に使用することもできます。

import LabelPlacement from '@site/static/usage/v8/select/label-placement/index.md';

<LabelPlacement />

### Label Slot

プレーンテキストのラベルは `label` プロパティで渡すべきですが、カスタムHTMLが必要な場合は、代わりに `label` スロットで渡すことができます。

import LabelSlot from '@site/static/usage/v8/select/label-slot/index.md';

<LabelSlot />

### No Visible Label

表示するラベルが必要ない場合でも、開発者は`aria-label`を指定する必要があります

import NoVisibleLabel from '@site/static/usage/v8/select/no-visible-label/index.md';

<NoVisibleLabel />

## Single Selection

デフォルトでは、selectを使用すると、ユーザは1つのOptionだけを選択できます。Alertのインターフェースでは、Optionのリストがradio button形式で表示されます。action sheetインタフェースは、1つの値選択でのみ使用できます。selectコンポーネントの値は、選択したオプションの値の値を受け取ります。

単一選択時のキーボード操作については、以下の[キーボード操作](#single-selection-1)のセクションで説明しています。

import SingleSelectionExample from '@site/static/usage/v8/select/basic/single-selection/index.md';

<SingleSelectionExample />

## 複数選択

select に `multiple` 属性を追加することで、ユーザは複数のオプションを選択することができます。複数のオプションを選択できる場合、アラート、ポップオーバー、またはモーダルオーバーレイは、チェックボックススタイルのオプションリストをユーザに提示します。select コンポーネントの値は、選択されたすべてのオプション値の配列を受け取ります。

:::note

注意: `action-sheet` インターフェースは複数選択では動作しません。

:::

複数選択時のキーボード操作については、以下の[キーボード操作](#multiple-selection-1)のセクションで説明しています。

import MultipleSelectionExample from '@site/static/usage/v8/select/basic/multiple-selection/index.md';

<MultipleSelectionExample />

## インターフェイス

デフォルトでは、selectは [ion-alert](alert.md) を使用してアラートのオプションのオーバーレイを開きます。インターフェイスは、`interface` プロパティに `action-sheet`、`popover`、`modal` を渡すことで、[ion-action-sheet](action-sheet.md)、[ion-popover](popover.md)、[ion-modal](modal.md) を使用するように変更することができます。それぞれのインターフェースの制限事項については、他のセクションを参照してください。

### Alert

import AlertExample from '@site/static/usage/v8/select/basic/single-selection/index.md';

<AlertExample />


### Action Sheet

import ActionSheetExample from '@site/static/usage/v8/select/interfaces/action-sheet/index.md';

<ActionSheetExample />

### Popover

import PopoverExample from '@site/static/usage/v8/select/interfaces/popover/index.md';

<PopoverExample />

### Modal

import ModalExample from '@site/static/usage/v8/select/interfaces/modal/index.md';

<ModalExample />

## Responding to Interaction

Select とユーザのインタラクションを処理する主な方法は、 `ionChange` イベント、 `ionDismiss` イベント、 `ionCancel` イベントです。これらのイベントやselectが発生するその他のイベントの詳細については、[Events](#events)を参照してください。

import RespondingToInteractionExample from '@site/static/usage/v8/select/basic/responding-to-interaction/index.md';

<RespondingToInteractionExample />

## オブジェクト値の参照

Selectの値にオブジェクトを使用する場合、Selectの値のidentityはそのままで、サーバやデータベースから取得したオブジェクトのidentityが変わってしまうことがあります。例えば、希望するオブジェクト値を持つ既存のレコードがSelectに読み込まれたが、新しく取得されたselectオプションのIDが異なる場合、このようなことが起こりえます。その結果、Selectは、元のSelectがそのまま残っているにもかかわらず、全く値がないように見えることになります。

デフォルトでは、Select はオプションが選択されているかどうかを決定するために厳密な等式 (`===`) を使用します。これは、プロパティ名または関数を `compareWith` プロパティに指定することでオーバーライドできます。

### Using compareWith

import UsingCompareWithExample from '@site/static/usage/v8/select/objects-as-values/using-comparewith/index.md';

<UsingCompareWithExample />

### Object Values and Multiple Selection

import ObjectValuesAndMultipleSelectionExample from '@site/static/usage/v8/select/objects-as-values/multiple-selection/index.md';

<ObjectValuesAndMultipleSelectionExample />

## Justification
  
開発者は `justify` プロパティを使って、ラベルとコントロールの行の詰め方をコントロールすることができる。

import JustifyExample from '@site/static/usage/v8/select/justify/index.md';

<JustifyExample />

## Filled Selects

Material DesignはセレクトにFilledスタイルを提供します。select の `fill` プロパティは `"solid"` または `"outline"` のいずれかに設定できます。

iOSでは、Selectの `mode` を `md` に設定することで、Filled Selectsを使うことができます。

:::warning
Selects that use `fill` should not be used in an `ion-item` due to styling conflicts between the components.
:::

import FillExample from '@site/static/usage/v8/select/fill/index.md';

<FillExample />

## Select Buttons

アラートは `Cancel` と `OK` の2つのボタンをサポートしている。それぞれのボタンのテキストは `cancelText` と `okText` プロパティを使ってカスタマイズすることができます。

`action-sheet` と `popover` インターフェースには `OK` ボタンがありません。オプションのいずれかをクリックすると自動的にオーバーレイが閉じ、その値が選択されます。 `popover` インターフェースには `Cancel` ボタンがなく、背景をクリックするとオーバーレイが閉じます。

The `modal` interface has a single `Close` button in the header. This button is only responsible for dismissing the modal. Any selections made will persist
after clicking this button or if the modal is dismissed using an alternative method.

import ButtonTextExample from '@site/static/usage/v8/select/customization/button-text/index.md';

<ButtonTextExample />

## インターフェイスオプション

selectはalert、action sheet、popover、modalの各インターフェイスを使用するので、`interfaceOptions`プロパティを通してこれらのコンポーネントにオプションを渡すことができます。これを使用して、カスタムヘッダー、サブヘッダー、CSS クラスなどを渡すことができます。

各インタフェースが受け付けるプロパティについては、[ion-alert docs](alert.md), [ion-action-sheet docs](action-sheet.md), [ion-popover docs](popover.md), [ion-modal docs](modal.md) を参照してください。
を参照してください。

注意: `alert` インターフェイスでは、`interfaceOptions` は `inputs` や `buttons` を上書きしません。

import InterfaceOptionsExample from '@site/static/usage/v8/select/customization/interface-options/index.md';

<InterfaceOptionsExample />

## Start and End Slots

The `start` and `end` slots can be used to place icons, buttons, or prefix/suffix text on either side of the select. If the slot content is clicked, the select will not open.

:::note
In most cases, [Icon](./icon.md) components placed in these slots should have `aria-hidden="true"`. See the [Icon accessibility docs](https://ionicframework.com/docs/api/icon#accessibility) for more information.

If slot content is meant to be interacted with, it should be wrapped in an interactive element such as a [Button](./button.md). This ensures that the content can be tabbed to.
:::

import StartEndSlots from '@site/static/usage/v8/select/start-end-slots/index.md';

<StartEndSlots />

## カスタマイズ

Selectコンポーネントには2つのユニットがあり、それぞれ別々にスタイルを設定する必要があります。 `ion-select`要素は、ビュー上で選択された値、ない場合はプレースホルダ、ドロップダウンのアイコンによって表現されます。インターフェイスは上記の[インターフェイス](#interfaces)セクションで定義されており、`ion-select`をクリックしたときに開くダイアログです。インターフェイスには `ion-select-option` 要素を追加することで定義されるすべてのオプションが含まれています。以下のセクションでは、これらのスタイリングの違いについて説明します。

### Select要素のスタイリング

前述の通り、`ion-select`要素は値、プレースホルダ、ビューに表示されるアイコンのみで構成されています。これをカスタマイズするには、CSSと[CSSカスタムプロパティ](#css-custom-properties)を組み合わせてスタイルを設定します。

また、必要な[ブラウザサポート](https://caniuse.com/#feat=mdn-css_selectors_part)によっては、CSSのシャドウパーツを使用してセレクトのスタイルを設定することもできます。 `part` を使用することで、要素上の任意の CSS プロパティを対象とすることができることに注意してください。

import StylingSelectExample from '@site/static/usage/v8/select/customization/styling-select/index.md';

<StylingSelectExample />

### セレクトインターフェースのスタイリング

インターフェイス・ダイアログのカスタマイズは、そのインターフェイスのドキュメントのスタイリングセクション（CSS shadow parts, CSS custom properties, and slots）に
従って行ってください。

- [Alert](alert.md#css-shadow-parts)
- [Action Sheet](action-sheet.md#css-shadow-parts)
- [Popover](popover.md#css-shadow-parts)
- [Modal](modal.md#css-shadow-parts)

しかし、セレクト・オプションは、スタイルを簡単にするためにクラスを設定し、オーバーレイ・オプションにクラスを渡すことができます。オプションをカスタマイズする使用例については、[セレクト・オプションのドキュメント](select-option.md)を参照してください。

### Custom Toggle Icons

選択テキストの隣に表示されるアイコンは、`toggleIcon` プロパティと `expandedIcon` プロパティを使用して、任意の [Ionicon](https://ionic.io/ionicons) に設定することができます。

import CustomToggleIconsExample from '@site/static/usage/v8/select/customization/custom-toggle-icons/index.md';

<CustomToggleIconsExample />

### アイコンの反転動作

デフォルトでは、セレクトを開いているとき、トグルアイコンは `md` モードでは自動的に回転し、`ios` モードでは静止します。この動作はCSSを使ってカスタマイズすることができます。

以下の例では[custom `toggleIcon`](#custom-toggle-icons)を使って、`ios`モードでのトグルアイコンの反転動作をより分かりやすく説明しています。

import IconFlipBehaviorExample from '@site/static/usage/v8/select/customization/icon-flip-behavior/index.md';

<IconFlipBehaviorExample />

## Typeahead Component

Typeaheadまたはオートコンプリート機能は、既存のIonicコンポーネントを使用して構築できます。利用可能なスクリーンスペースを最大限に活用するために、`ion-modal`を使用することをお勧めします。

import TypeaheadExample from '@site/static/usage/v8/select/typeahead/index.md';

<TypeaheadExample />

## Helper & Error Text

Helper and error text can be used inside of a select with the `helperText` and `errorText` property. The error text will not be displayed unless the `ion-invalid` and `ion-touched` classes are added to the `ion-select`. This ensures errors are not shown before the user has a chance to enter data.

In Angular, this is done automatically through form validation. In JavaScript, React and Vue, the class needs to be manually added based on your own validation.

import HelperError from '@site/static/usage/v8/select/helper-error/index.md';

<HelperError />

## Interfaces

### SelectChangeEventDetail

```typescript
interface SelectChangeEventDetail<T = any> {
  value: T;
}
```

### SelectCustomEvent

必須ではありませんが、このインターフェイスを `CustomEvent` インターフェイスの代わりに使用することで、このコンポーネントから発行される Ionic イベントをより強力に片付けすることができます。

```typescript
interface SelectCustomEvent<T = any> extends CustomEvent {
  detail: SelectChangeEventDetail<T>;
  target: HTMLIonSelectElement;
}
```

## 従来のセレクト構文からの移行

Ionic 7.0では、よりシンプルなセレクト構文が導入されました。この新しい構文は、セレクトのセットアップに必要な定型文を減らし、アクセシビリティの問題を解決し、開発者のエクスペリエンスを向上させます。

開発者はこの移行をセレクトごとに行うことができます。開発者は従来の構文を使い続けることもできますが、できるだけ早く移行することをお勧めします。


### 最新構文の使用

最新の構文を使用するには、2つのステップがあります：

1. 1. `ion-label` を削除し、代わりに `ion-select` の `label` プロパティを使用する。ラベルの配置は `ion-select` の `labelPlacement` プロパティで設定できる。
2. fill` と `shape` を `ion-item` から `ion-select` に移動する。

import Migration from '@site/static/usage/v8/select/migration/index.md';

<Migration />

### レガシー構文の使用

Ionicは、アプリがモダンなセレクト構文を使用しているかどうかをヒューリスティックで検出します。場合によっては、レガシー構文を使い続けた方が望ましいこともあります。開発者は `ion-select` の `legacy` プロパティを `true` に設定することで、その入力インスタンスにレガシー構文を使用させることができます。

## Accessibility

### Keyboard Interactions

Ionic's keyboard interactions follow the implementation patterns of the web instead of the native iOS select for a consistent experience across all platforms.

These keyboard interactions apply to all `ion-select` elements when the following conditions are met:
- The select is closed.
- The select is focused.
- The select is not disabled.

| Key                | Description                                                  |
| ------------------ | ------------------------------------------------------------ |
| <kbd>Enter</kbd>   | Opens the overlay and focuses on the first selected option. If there is no selected option, then it focuses on the first option. |
| <kbd>Space</kbd>   | Opens the overlay and focuses on the first selected option. If there is no selected option, then it focuses on the first option. |

#### Single Selection

Single selection keyboard interaction follows the [ARIA implementation patterns of a radio](https://www.w3.org/WAI/ARIA/apg/patterns/radio/).

These keyboard interactions apply to `ion-action-sheet`, `ion-alert`, `ion-popover`, and `ion-modal` elements when the overlay is presented and focused.

| Key                   | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| <kbd>ArrowDown</kbd>  | Focuses and selects the next option in the list. If there is no next option, selection will cycle to the first option. |
| <kbd>ArrowLeft</kbd>  | Focuses and selects the previous option in the list. If there is no previous option, selection will cycle to the last option. |
| <kbd>ArrowRight</kbd> | Focuses and selects the next option in the list. If there is no next option, selection will cycle to the first option. |
| <kbd>ArrowUp</kbd>    | Focuses and selects the previous option in the list. If there is no previous option, selection will cycle to the last option. |
| <kbd>Enter</kbd>      | If an option is focused, it will select the option. Overlays **without** an 'OK' button will commit the value immediately, dismiss the overlay and return focus to the `ion-select` element.<br /><br/>If the 'OK' button is focused, it will save the user's selection, dismiss the overlay and return focus to the `ion-select` element. |
| <kbd>Escape</kbd>     | Closes the overlay without changing the submitted option. Returns the focus back to the `ion-select` element. |
| <kbd>Space</kbd>      | If the focused radio button is not checked, unchecks the currently checked radio button and checks the focused radio button. Otherwise, does nothing. If the overlay does not have an 'OK' button, the value will be committed immediately and the overlay will dismiss. |
| <kbd>Tab</kbd>        | Moves focus to the next focusable element (cancel button, 'OK' button, or either the selection or the first option) on the overlay. If the next focusable element is an option, then it will focus on the selected option, otherwise it will focus the first option. |

#### Multiple Selection

Multiple selection keyboard interaction follows the [ARIA implementation patterns of a checkbox](https://www.w3.org/WAI/ARIA/apg/patterns/checkbox/).

These keyboard interactions apply to `ion-alert`, `ion-popover`, and `ion-modal` elements when the overlay is presented and multiple selection is enabled.

| Key                | Description                                                  |
| ------------------ | ------------------------------------------------------------ |
| <kbd>Enter</kbd>   | When the 'OK' button is focused, it will save the user's selection, dismiss the overlay, and return focus to the `ion-select` element. |
| <kbd>Escape</kbd>  | Closes the overlay without changing the submitted option(s). Returns the focus back to the `ion-select` element. |
| <kbd>Space</kbd>   | Selects or deselects the currently focused option. This does not deselect the other selected options. If the overlay does not have an 'OK' button, the value will be committed immediately. |
| <kbd>Tab</kbd>     | Move focus to the next focusable element (cancel button, 'OK' button, or any of the options) on the overlay. If the next focusable element is the options list, then it should iterate through each option. |

## Properties
<Props />

## イベント
<Events />

## メソッド
<Methods />

## CSS Shadow Parts
<Parts />

## CSS カスタムプロパティ
<CustomProps />

## Slots
<Slots />
