# Typography

### What is Typography

\
Typography in Angular Material refers to the visual style and arrangement of text within the user interface of your Angular application. Angular Material provides a typography system that helps you define and maintain consistent and visually appealing text styles throughout your application. Here are key aspects of typography in Angular Material:

1. **Typography Configuration**: Angular Material allows you to configure typography settings, including font families, font sizes, line heights, and other text-related properties.
2. **Typographic Styles**: You can define different typographic styles for various parts of your application, such as headings, body text, buttons, and more. This ensures a consistent and harmonious look and feel.
3. **Responsive Typography**: Angular Material supports responsive typography, which means you can define different font sizes and styles for different screen sizes and device types. This helps in creating a responsive design that adapts to various viewport sizes.
4. **Roboto Font**: By default, Angular Material uses the Roboto font as the primary typeface, which is a well-designed and highly legible font suitable for web and mobile applications.
5. **Theme-Based Typography**: Typography settings can be customized as part of your application's theme. This allows you to maintain consistent typography throughout your app by defining typography-related variables in your theme's SCSS file.
6. **Typography Classes**: Angular Material provides a set of CSS classes for applying predefined typographic styles to your elements. For example, you can use classes like **`mat-h1`**, **`mat-h2`**, **`mat-body-1`**, etc., to apply specific typographic styles.
7. **Accessibility**: Angular Material takes accessibility into account when defining typography styles. Text elements are designed to be easily readable and accessible to users with disabilities.

### Define Typography

Define typography in theme's SCSS file

```scss
$heading-font-family: "'Work Sans', sans-serif";
$typography: mat-typography-config(
  $display-4: mat-typography-level(112px, $font-family: $heading-font-family),
  $display-3: mat-typography-level(56px, $font-family: $heading-font-family),
  $display-2: mat-typography-level(45px, $font-family: $heading-font-family),
  $display-1: mat-typography-level(34px, $font-family: $heading-font-family),
  $headline: mat-typography-level(24px, $font-family: $heading-font-family),
  $title: mat-typography-level(20px, $font-family: $heading-font-family),
);
```

below are the list of typography class names

```
//these list of typography class names which we can directly use in html files
headline-1	One-off header, usually at the top of the page (e.g. a hero header).
headline-2	One-off header, usually at the top of the page (e.g. a hero header).
headline-3	One-off header, usually at the top of the page (e.g. a hero header).
headline-4	One-off header, usually at the top of the page (e.g. a hero header).
headline-5	Section heading corresponding to the <h1> tag.
headline-6	Section heading corresponding to the <h2> tag.
subtitle-1	Section heading corresponding to the <h3> tag.
subtitle-2	Section heading corresponding to the <h4> tag.
body-1	Base body text.
body-2	Secondary body text.
caption	Smaller body and hint text.
button	Buttons and anchors.

// CSS class Level name Native elements
.mat-display-4	display-4	None
.mat-display-3	display-3	None
.mat-display-2	display-2	None
.mat-display-1	display-1	None
.mat-h1 or .mat-headline	headline	<h1>
.mat-h2 or .mat-title	title	<h2>
.mat-h3 or .mat-subheading-2	subheading-2	<h3>
.mat-h4 or .mat-subheading-1	subheading-1	<h4>
.mat-h5	None	<h5>
.mat-h6	None	<h6>
.mat-body or .mat-body-1	body-1	Body text
.mat-body-strong or .mat-body-2	body-2	None
.mat-small or .mat-caption	caption	None
```

### Custom Typography

In our Sunbird Ed Angular Material application, we have tailored typography classes to suit our design preferences. Additionally, we've adopted the usage of "rem" units instead of "px" for better responsiveness, and we've opted for the "**Noto Sans**" font family to achieve the desired typographic style.

We've set up custom typography styles within the "**\_typography.scss**" file located in the "**mat-themes**" directory, as demonstrated below:

{% code title="_typography.scss" %}
```scss
$custom-typography: mat.define-typography-config(
  $font-family: null,
  $display-4: mat.define-typography-level(7rem, 7rem, 300, $letter-spacing: -0.05em),
  $display-3: mat.define-typography-level(3.5rem, 3.5rem, 400, $letter-spacing: -0.02em),
  $display-2: mat.define-typography-level(2.8125rem, 3rem, 400, $letter-spacing: -0.005em),
  $display-1: mat.define-typography-level(2.125rem, 2.5rem, 400),
  $headline: mat.define-typography-level(1.5rem, 2rem, 400),
  $title: mat.define-typography-level(1.25rem, normal, 500),
  $subheading-2: mat.define-typography-level(1rem, 1.25rem, 500),
  $subheading-1: mat.define-typography-level(1rem, 1.25rem, 400),
  $body-2: mat.define-typography-level(0.875rem, 1.25rem, 500),
  $body-1: mat.define-typography-level(0.875rem, 1.25rem, 400),
  $caption: mat.define-typography-level(0.75rem, 1.25rem, 400),
  $button: mat.define-typography-level(0.75rem, 1rem, 500),
  $input: mat.define-typography-level(inherit, 1.125, 400),
);
```
{% endcode %}

To customize component typography for entire application, we can pass our custom typography config to the `core` mixin in "**themes.scss**" file

```scss
@include mat.core($custom-typography);
```

With these custom typography settings in place, you can now utilize custom typography class names alongside the standard ones provided by Angular Material, such as "**mat-body-1**" and "**mat-title**"

These class names have been applied within the example components of the Sunbird Ed Angular Material application.

**main-header.component.html**

```html
 <h1 class="mat-title mb-4" tabindex="0" role="heading" aria-level="2">{{showingResu
```

**course-progress.component.html**

```html
<p class="mat-body-1">{{resourceService?.messages?.stmsg?.m0132}}</p>
```

**data-chart.component.html**

```html
<p class="mat-display-1 font-weight-bold mb-8">{{bigNumberChart?.data}} </p>
```

For more detailed information, please refer to the following link:

[**Angular Material Typography Guide**](https://v14.material.angular.io/guide/typography)
