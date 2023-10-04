# Installation

### Install Angular Material

Use the Angular CLI's installation schematic to set up your Angular Material project by running the following command:

```bash
ng add @angular/material
```

For detailed installation instructions, please refer to the following link: [**Angular Material Installation Guide**](https://v14.material.angular.io/guide/getting-started).

The `ng add` command will install Angular Material, the Component Dev Kit(CDK), Angular Animations and it will ask you the following questions to determine which features to include:

1. Choose a prebuilt theme name, or "custom" for a custom theme. These are the list of prebuilt themes.

<table><thead><tr><th>Theme</th><th width="216.33333333333331">Light or dark</th><th>Palettes (primary,accent,warn)</th></tr></thead><tbody><tr><td>deeppurple-amber.css</td><td>Light</td><td>deep-purple, amber, red</td></tr><tr><td>indigo-pink.css</td><td>Light</td><td>indigo, pink, red</td></tr><tr><td>pink-bluegrey.css</td><td>Dark</td><td>pink, blue-grey, red</td></tr><tr><td>purple-green.css</td><td>Dark</td><td>purple, green, red</td></tr></tbody></table>

Once you've included these files, the CSS for every component in the library will be available, and the selected theme CSS file will be automatically included in your angular.json configuration.

```javascript
"styles": [
    "./node_modules/@angular/material/prebuilt-themes/indigo-pink.css",
]
```

{% hint style="info" %}
If you are creating your custom theme, you can manually remove the prebuilt theme CSS file (e.g., indigo-pink.css) from the angular.json file.
{% endhint %}

{% hint style="success" %}
You're done! Angular Material is now configured to be used in your application.
{% endhint %}

### Browser Animations

Set up browser animations for Angular Material:

Importing the **BrowserAnimationsModule** into your application in the **app.module.ts** file activates Angular's animation system.&#x20;

Neglecting this import will lead to the disabling of the majority of Angular Material's animations.&#x20;

{% hint style="warning" %}
Failure to include this import will result in the deactivation of most of Angular Material's animations.
{% endhint %}

```javascript
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
```

Include the imported **BrowserAnimationsModule** in the **`imports`** array within the **`@NgModule`** decorator of your **app.module.ts** file.

{% code lineNumbers="true" %}
```javascript
@NgModule({
    declarations: [
        AppComponent
    ],
    imports: [
        BrowserAnimationsModule,
        CoreModule,
        CommonModule,
    ],
    bootstrap: [AppComponent],
    providers: [
        CacheService,
        ChatLibService,
    ],
})
```
{% endcode %}

For further details, please visit the following link:

[**https://zerotomastery.io/blog/angular-animations-and-examples/**](https://zerotomastery.io/blog/angular-animations-and-examples/)

### Import Modules

We've created a file named "**material.module.ts**" in which we've globally imported all Angular Material modules.

{% code lineNumbers="true" %}
```javascript
import {NgModule} from '@angular/core';
import {A11yModule} from '@angular/cdk/a11y';
import {CdkAccordionModule} from '@angular/cdk/accordion';
import {ClipboardModule} from '@angular/cdk/clipboard';
import {DragDropModule} from '@angular/cdk/drag-drop';
import {PortalModule} from '@angular/cdk/portal';
import {ScrollingModule} from '@angular/cdk/scrolling';
import {CdkStepperModule} from '@angular/cdk/stepper';
import {CdkTableModule} from '@angular/cdk/table';
import {CdkTreeModule} from '@angular/cdk/tree';
import {MatAutocompleteModule} from '@angular/material/autocomplete';
import {MatBadgeModule} from '@angular/material/badge';
import {MatBottomSheetModule} from '@angular/material/bottom-sheet';
import {MatButtonModule} from '@angular/material/button';
import {MatButtonToggleModule} from '@angular/material/button-toggle';
import {MatCardModule} from '@angular/material/card';
import {MatCheckboxModule} from '@angular/material/checkbox';
import {MatChipsModule} from '@angular/material/chips';
import {MatStepperModule} from '@angular/material/stepper';
import {MatDatepickerModule} from '@angular/material/datepicker';
import {MatDialogModule} from '@angular/material/dialog';
import {MatDividerModule} from '@angular/material/divider';
import {MatExpansionModule} from '@angular/material/expansion';
import {MatGridListModule} from '@angular/material/grid-list';
import {MatIconModule} from '@angular/material/icon';
import {MatInputModule} from '@angular/material/input';
import {MatListModule} from '@angular/material/list';
import {MatMenuModule} from '@angular/material/menu';
import {MatNativeDateModule, MatRippleModule} from '@angular/material/core';
import {MatPaginatorModule} from '@angular/material/paginator';
import {MatProgressBarModule} from '@angular/material/progress-bar';
import {MatProgressSpinnerModule} from '@angular/material/progress-spinner';
import {MatRadioModule} from '@angular/material/radio';
import {MatSelectModule} from '@angular/material/select';
import {MatSidenavModule} from '@angular/material/sidenav';
import {MatSliderModule} from '@angular/material/slider';
import {MatSlideToggleModule} from '@angular/material/slide-toggle';
import {MatSnackBarModule} from '@angular/material/snack-bar';
import {MatSortModule} from '@angular/material/sort';
import {MatTableModule} from '@angular/material/table';
import {MatTabsModule} from '@angular/material/tabs';
import {MatToolbarModule} from '@angular/material/toolbar';
import {MatTooltipModule} from '@angular/material/tooltip';
import {MatTreeModule} from '@angular/material/tree';
import {OverlayModule} from '@angular/cdk/overlay';
import {BidiModule} from '@angular/cdk/bidi';
```
{% endcode %}

Add the Angular Material modules you imported to the **`imports`** array inside the **`@NgModule`** decorator within the **"material.module.ts"** file.

{% code lineNumbers="true" %}
```javascript
@NgModule({
  exports: [
    A11yModule,
    CdkAccordionModule,
    ClipboardModule,
    CdkStepperModule,
    CdkTableModule,
    CdkTreeModule,
    DragDropModule,
    MatAutocompleteModule,
    MatBadgeModule,
    MatBottomSheetModule,
    MatButtonModule,
    MatButtonToggleModule,
    MatCardModule,
    MatCheckboxModule,
    MatChipsModule,
    MatStepperModule,
    MatDatepickerModule,
    MatDialogModule,
    MatDividerModule,
    MatExpansionModule,
    MatGridListModule,
    MatIconModule,
    MatInputModule,
    MatListModule,
    MatMenuModule,
    MatNativeDateModule,
    MatPaginatorModule,
    MatProgressBarModule,
    MatProgressSpinnerModule,
    MatRadioModule,
    MatRippleModule,
    MatSelectModule,
    MatSidenavModule,
    MatSliderModule,
    MatSlideToggleModule,
    MatSnackBarModule,
    MatSortModule,
    MatTableModule,
    MatTabsModule,
    MatToolbarModule,
    MatTooltipModule,
    MatTreeModule,
    OverlayModule,
    PortalModule,
    ScrollingModule,
    BidiModule
  ]
})
```
{% endcode %}

We imported the previously created "**material.module.ts**" file into the "**shared.module.ts**" file.

```javascript
import { MaterialModule } from './modules/material/material.module';
```

In the **"shared.module.ts"** file, include the imported "**MaterialModule**" in both the **`imports`** and **`exports`** arrays within the **`@NgModule`** decorator.
