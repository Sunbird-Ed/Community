# Buttons

1. **Button Variants**: Angular Material [**buttons**](https://v14.material.angular.io/components/button/overview) come in different variants, such as raised, outlined, and FAB (Floating Action Button). Choose the button variant that best suits your design requirements. As an example within our application, we utilized the following code, resulting in the following output:&#x20;

```html
<button mat-raised-button color="accent">CHANGE PREFERENCE</button>
```

<figure><img src="../../../../../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

2. **CSS Classes**: Add custom CSS classes to Angular Material buttons to apply your own styles. Utilize the `class` attribute to assign classes to button elements.

For the code example mentioned above, we incorporated a custom class and associated CSS styles in the **`_buttons.scss`** file.

```markup
<button mat-raised-button color="accent" class="button-rounded">CHANGE PREFERENCE</button>
```

```scss
.button-rounded {
  &.mat-raised-button {
    border-radius: 2rem;
  }
}
```

The CSS code provided is used to override the default styles of the `mat-raised-button` component, resulting in the following visual output:

<figure><img src="../../../../../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

3. **Button Theming**: Customize button theming by adjusting primary, accent, and warn colors within your custom theme. These colors impact button backgrounds, text, and other visual elements.&#x20;

We customized the button theme to use the "success" color, which is represented by the green palette, and here is the corresponding code:

```markup
<button mat-raised-button color="success" class="button-rounded">CHANGE PREFERENCE</button>
```

```scss
%mat-success {
  $success: mat.define-palette(mat.$green-palette);
  background-color: mat.get-color-from-palette($success, 500);
  color: mat.get-color-from-palette($success, 500-contrast);
}

.mat-raised-button.mat-success {
  @extend %mat-success;
}
```

1. **%mat-success (SCSS Placeholder)**:
   * `%mat-success` is a SCSS placeholder selector. It is not a class or ID that will be directly applied to HTML elements. Instead, it serves as a reusable block of styles that can be extended or included in other selectors.
2. **Palette Definition**:
   * `$success: mat.define-palette(mat.$green-palette);`
     * This line defines a SCSS variable `$success` and assigns it a color palette. It appears to be creating a custom palette called "success" by referencing Angular Material's built-in `$green-palette`.
3. **Background Color and Text Color**:
   * `background-color: mat.get-color-from-palette($success, 500);`
     * Sets the background color of elements using the color from the `$success` palette at the 500 shade (presumably a shade of green).
   * `color: mat.get-color-from-palette($success, 500-contrast);`
     * Sets the text color (foreground color) of elements using the color from the `$success` palette at the 500-contrast shade. This typically ensures that text on the button has sufficient contrast against the background.
4.  **Button Selectors**

    `.mat-raised-button.mat-success { @extend %mat-success; }`

    * This block of CSS code applies the styles defined in `%mat-success` to buttons with the specified classes, effectively applying the custom "success" theme to these button types.

The end result is as follows:

<figure><img src="../../../../../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
