```html
<ion-breadcrumbs [maxItems]="4" (ionCollapsedClick)="presentPopover($event)">
  <ion-breadcrumb href="#home">Home</ion-breadcrumb>
  <ion-breadcrumb href="#electronics">Electronics</ion-breadcrumb>
  <ion-breadcrumb href="#photography">Photography</ion-breadcrumb>
  <ion-breadcrumb href="#cameras">Cameras</ion-breadcrumb>
  <ion-breadcrumb href="#film">Film</ion-breadcrumb>
  <ion-breadcrumb href="#35mm">35 mm</ion-breadcrumb>
</ion-breadcrumbs>
<ion-popover #popover [isOpen]="isOpen" (didDismiss)="isOpen = false">
  <ng-template>
    <ion-content>
      <ion-list>
        @for (breadcrumb of collapsedBreadcrumbs; track breadcrumb; let last = $last) {
        <ion-item [href]="breadcrumb.href" [lines]="last ? 'none' : null">
          <ion-label>{{ breadcrumb.textContent }}</ion-label>
        </ion-item>
        }
      </ion-list>
    </ion-content>
  </ng-template>
</ion-popover>
```
