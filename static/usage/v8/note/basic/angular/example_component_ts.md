```ts
import { Component } from '@angular/core';
import { IonNote } from '@ionic/angular/standalone';

@Component({
  selector: 'app-example',
  templateUrl: 'example.component.html',
  styleUrls: ['example.component.css'],
  imports: [IonNote],
})
export class ExampleComponent {}
```