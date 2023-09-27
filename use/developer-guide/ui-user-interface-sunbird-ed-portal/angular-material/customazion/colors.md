# Colors

In Angular Material, colors play a significant role in defining the visual style and theming of your web application. Angular Material provides a predefined color palette system to help you maintain consistent and visually appealing color schemes throughout your application.&#x20;

We've created a "**@mixin**" for managing colors, named "**theme-var-colors**" within the "**\_colors.scss**" file located in the "**mat-themes**" folder. This mixin has been included in the "**themes.scss**" file.

{% code title="_colors.scss" %}
```scss
@mixin theme-var-colors($theme) {
    //code will come here
}
```
{% endcode %}

All the mixins need to be included in the "**app-themes**" section within the "**themes.scss**" file.

{% code title="themes.scss" %}
```scss
 @mixin app-themes($theme) {
     @include theme-var-colors($theme);
 }
```
{% endcode %}

### Primary Color

The primary color is the main color used for the majority of your application's elements, such as headers, buttons, and backgrounds.

* **`mat-primary`** (default): A predefined color palette that typically represents your application's primary brand color.
* Custom colors: You can define your own custom primary color palette by specifying your preferred color in CSS or through Angular's theming system.

```scss
$primary: map.get($color-config, 'primary');
$color-primary: mat.get-color-from-palette($primary);
--color-primary: #{$color-primary};

```

**Primary color variations**

```scss
  $color-primary-50: mat.get-color-from-palette($primary, 50);
  $color-primary-100: mat.get-color-from-palette($primary, 100);
  $color-primary-200: mat.get-color-from-palette($primary, 200);
  $color-primary-300: mat.get-color-from-palette($primary, 300);
  $color-primary-400: mat.get-color-from-palette($primary, 400);
  $color-primary-500: mat.get-color-from-palette($primary, 500);
  $color-primary-600: mat.get-color-from-palette($primary, 600);
  $color-primary-700: mat.get-color-from-palette($primary, 700);
  $color-primary-800: mat.get-color-from-palette($primary, 800);
  $color-primary-900: mat.get-color-from-palette($primary, 900);
  --color-primary-50: #{$color-primary-50};
  --color-primary-100: #{$color-primary-100};
  --color-primary-200: #{$color-primary-200};
  --color-primary-300: #{$color-primary-300};
  --color-primary-400: #{$color-primary-400};
  --color-primary-500: #{$color-primary-500};
  --color-primary-600: #{$color-primary-600};
  --color-primary-700: #{$color-primary-700};
  --color-primary-800: #{$color-primary-800};
  --color-primary-900: #{$color-primary-900};
```

### Accent Color

The accent color is used to highlight certain UI elements and add visual interest to your application. It complements the primary color.&#x20;

* **`mat-accent`**: A predefined color palette that typically represents your application's primary brand color.
* Custom colors: You can define your own custom primary color palette by specifying your preferred color in CSS or through Angular's theming system.

```scss
$accent: map.get($color-config, 'accent');
$color-accent: mat.get-color-from-palette($accent);
--color-accent: #{$color-accent};
```

**Accent color variations:**

```scss
  $color-accent-50: mat.get-color-from-palette($accent, 50);
  $color-accent-100: mat.get-color-from-palette($accent, 100);
  $color-accent-200: mat.get-color-from-palette($accent, 200);
  $color-accent-200-contrast: mat.get-color-from-palette($accent, 200-contrast);
  $color-accent-300: mat.get-color-from-palette($accent, 300);
  $color-accent-400: mat.get-color-from-palette($accent, 400);
  $color-accent-500: mat.get-color-from-palette($accent, 500);
  $color-accent-600: mat.get-color-from-palette($accent, 600);
  $color-accent-700: mat.get-color-from-palette($accent, 700);
  $color-accent-800: mat.get-color-from-palette($accent, 800);
  $color-accent-900: mat.get-color-from-palette($accent, 900);
  --color-accent-50: #{$color-accent-50};
  --color-accent-100: #{$color-accent-100};
  --color-accent-200: #{$color-accent-200};
  --color-accent-200-contrast: #{$color-accent-200-contrast};
  --color-accent-300: #{$color-accent-300};
  --color-accent-400: #{$color-accent-400};
  --color-accent-500: #{$color-accent-500};
  --color-accent-600: #{$color-accent-600};
  --color-accent-700: #{$color-accent-700};
  --color-accent-800: #{$color-accent-800};
  --color-accent-900: #{$color-accent-900};
```

### Warn color

The warn color is used to indicate errors or warnings in your application.

* **`mat-warn`**: A predefined color palette that typically represents your application's primary brand color.
* Custom colors: You can define your own custom primary color palette by specifying your preferred color in CSS or through Angular's theming system.

```scss
$warn: map.get($color-config, 'warn');
$color-warn: mat.get-color-from-palette($warn);
--color-warn: #{$color-warn};
```

**Warn color variations:**

```scss
$color-warn-50:  mat.get-color-from-palette($warn, 50);
  $color-warn-100: mat.get-color-from-palette($warn, 100);
  $color-warn-200: mat.get-color-from-palette($warn, 200);
  $color-warn-300: mat.get-color-from-palette($warn, 300);
  $color-warn-400: mat.get-color-from-palette($warn, 400);
  $color-warn-500: mat.get-color-from-palette($warn, 500);
  --color-warn-50:  #{$color-warn-50};
  --color-warn-100: #{$color-warn-100};
  --color-warn-200: #{$color-warn-200};
  --color-warn-300: #{$color-warn-300};
  --color-warn-400: #{$color-warn-400};
  --color-warn-500: #{$color-warn-500};
```

### Info Color

This color is used to to convey informational messages or elements in a user interface

```scss
$info: mat.define-palette(mat.$blue-palette);
$color-info: mat.get-color-from-palette($info);
--color-info: #{$color-info};
```

### Success Color

This color is often used to indicate that a task or action has been completed successfully or that a positive status or outcome has been achieved.

```scss
$success: mat.define-palette(mat.$green-palette);
$color-success: mat.get-color-from-palette($success);
--color-success: #{$color-success};
```

**Success color variations:**

```scss
$color-success-50:  mat.get-color-from-palette($success, 50);
  $color-success-100: mat.get-color-from-palette($success, 100);
  $color-success-200: mat.get-color-from-palette($success, 200);
  $color-success-300: mat.get-color-from-palette($success, 300);
  $color-success-400: mat.get-color-from-palette($success, 400);
  $color-success-500: mat.get-color-from-palette($success, 500);
  --color-success-50:  #{$color-success-50};
  --color-success-100: #{$color-success-100};
  --color-success-200: #{$color-success-200};
  --color-success-300: #{$color-success-300};
  --color-success-400: #{$color-success-400};
  --color-success-500: #{$color-success-500};
```

### Error Color

This color is used to indicate that an error or problem has occurred. It is a crucial visual cue that helps users quickly recognize and respond to issues within an application. The choice of color for an error message or error-related elements can vary, but red is a commonly used color for this purpose in many design systems.

```scss
$error: mat.define-palette(mat.$orange-palette);
$color-error: mat.get-color-from-palette($error);
--color-error: #{$color-error};
```

**Error color variations:**

```scss
  $color-error-50:  mat.get-color-from-palette($error, 50);
  $color-error-100: mat.get-color-from-palette($error, 100);
  $color-error-200: mat.get-color-from-palette($error, 200);
  $color-error-300: mat.get-color-from-palette($error, 300);
  $color-error-400: mat.get-color-from-palette($error, 400);
  $color-error-500: mat.get-color-from-palette($error, 500);
  --color-error-50:  #{$color-error-50};
  --color-error-100: #{$color-error-100};
  --color-error-200: #{$color-error-200};
  --color-error-300: #{$color-error-300};
  --color-error-400: #{$color-error-400};
  --color-error-500: #{$color-error-500};
```
