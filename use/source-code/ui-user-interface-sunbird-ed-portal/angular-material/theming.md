# Theming

### What is theming? <a href="#what-is-theming" id="what-is-theming"></a>

Angular Material's theming system lets you customize color, typography, and density styles for components in your application. The theming system is based on Google's Material Design specification.

Here are some key aspects of Angular Material Theming:

1. **Predefined Themes:** Angular Material provides a set of predefined themes that developers can choose from to quickly style their applications. These themes include various color schemes and typography settings. Developers can select a theme that best matches their application's branding or design requirements.
2. **Custom Theming:** While the predefined themes are a good starting point, Angular Material also allows developers to create custom themes tailored to their specific needs. This involves defining custom color palettes, typography settings, and component styles.
3. **Theme Variables:** To create custom themes, Angular Material relies on CSS variables, also known as CSS custom properties. These variables make it easy to define and change the theme's colors and styles in a consistent and maintainable way.
4. **Dynamic Theming:** Angular Material also supports dynamic theming, allowing you to change the theme of your application at runtime. This can be useful for implementing features like dark mode or offering users the ability to choose their preferred theme.

### Defining a theme

A **theme** is a collection of color, typography, and density options. Each theme includes three palettes that determine component colors:

* A **primary** palette for the color that appears most frequently throughout your application
* An **accent**, or _secondary_, palette used to selectively highlight key parts of your UI
* A **warn**, or _error_, palette used for warnings and error states

### Sass

Angular Material's theming APIs are built with **Sass.** This document assumes familiarity with CSS and Sass basics, including variables, functions, and mixins.

For more information about **sass**, please visit the following link: [**https://sass-lang.com/guide/**](https://sass-lang.com/guide/)

### Partials

Sass partials are small, reusable snippets of CSS that can be included in other Sass files, aiding in the modularization and organization of your stylesheets. These partial files are typically named with an underscore prefix, such as `_partial.scss`, to indicate to the Sass compiler that they should not be compiled into standalone CSS files.&#x20;

Here are some key points to note about Sass partials:

* **Partial File Naming Convention**: Sass partials are named with an underscore prefix (e.g., `_partial.scss`) to distinguish them from standalone CSS files.
* **Modularization**: Partials allow you to break down your styles into smaller, focused pieces, making it easier to manage specific aspects of your project, such as typography, colors, buttons, forms, or individual components.
* **Reusability**: You can import partials into multiple Sass files, promoting code reuse and ensuring consistent styles throughout your project.
* **Organization**: By grouping related partials and creating directories, you can maintain a logical and structured organization of your project's styles, enhancing readability and maintenance.

To implement theming in a Sunbird Ed Angular Material application, you generally leverage the Angular Material theming capabilities offered by the library. In our setup, we've established a folder named "**mat-themes**," which contains all the custom theme assets and configurations. Below is a list of partials:

1. \_buttons.scss
2. \_colors.scss
3. \_mat-badge.scss
4. \_mat-card.scss
5. \_mat-chips.scss
6. \_mat-dialog.scss
7. \_mat-expansion-panel
8. \_mat-form-field.scss
9. \_mat-list.scss
10. \_mat-sidebar.scss
11. \_mat-tab-group.scss
12. \_palette.scss
13. \_search.scss
14. \_template\_bg.scss
15. \_toolbar-menu.scss
16. \_toolbar-pageback.scss
17. \_typography.scss

{% hint style="info" %}
We will delve into each individual partial file in upcoming sessions.
{% endhint %}

### Import Partials

To include a Sass partial within another Sass file, you can utilize the `@import` directive followed by the partial's filename, excluding the underscore and the .scss extension. As an example, we imported all the previously mentioned partials into the **"includes.scss"** file, which is subsequently included in the "**mat-themes**" folder.

{% code lineNumbers="true" %}
```scss
@use "@angular/material" as mat;
@use "sass:map";
@import "./buttons";
@import "./colors";
@import './mat-badge';
@import './mat-card';
@import './mat-chips';
@import './mat-dialog';
@import './mat-expansion-panel';
@import './mat-form-field';
@import './mat-list';
@import './mat-sidebar';
@import './mat-tab-group';
@import './search';
@use './template_bg' as *;
@import "./toolbar-menu";
@import "./toolbar-pageback";
@import "./typography";
```
{% endcode %}

In summary, while **`@import`** is still valid in Sass, **`@use`** is recommended for modern projects as it provides better encapsulation, organization, and performance. It's particularly useful in larger codebases where avoiding naming conflicts and optimizing output CSS are essential considerations.

> ```scss
> @use "@angular/material" as mat;
> ```

The line of code you provided is using the `@use` directive in Sass to import the Angular Material library and create an alias `mat` for it. This alias allows you to reference Angular Material's styles, variables, mixins, and components in your Sass or SCSS files more easily and with better encapsulation.

Here's a breakdown of the code:

* **`@use`**: This is the Sass directive used to import external modules or files.
* **`"@angular/material"`**: This is the path to the Angular Material library. It's enclosed in double quotes to specify a module or package name. You can use the correct path to the Angular Material library in your project.
* **`as mat`**: This part of the code creates an alias `mat` for the imported Angular Material library. The alias allows you to access Angular Material's features using the `mat` namespace. For example, you can use **`mat.button`** to reference Angular Material's button styles or components.

> ```scss
> @use "sass:map";
> ```

The line of code **`@use "sass:map"`**`;` in Sass is importing the built-in Sass module called `map`. This module provides functionality for working with Sass maps, which are a data structure in Sass used to store key-value pairs.

In summary, Using Sass partials helps you maintain a well-organized, modular, and maintainable codebase for your styles, which is particularly useful in larger web development projects.
