---
description: >-
  The Classical Theme, featured in SB-Themes, embodies a timeless and
  conventional visual style. This theme offers users a classic aesthetic that
  exudes elegance and simplicity.
---

# Classical Theme in Sunbird-Ed portal

With carefully selected color palettes, typography, and design elements, the Classical Theme provides a familiar and sophisticated user experience, catering to those who appreciate a traditional design approach.

**Color Palette in SB-Themes:**

SB-Themes embraces a thoughtfully crafted color palette to enhance the visual experience in the Sunbird-Ed portal and mobile application. Key color variables include:

* **Primary Color:** `#024f9d` - Used for elements like buttons, headings, table titles, links, and toggles.
* **Secondary Color:** `#008840` - Employed for various interface elements, including buttons and hover states.
* **Tertiary Color (Warning):** `#e55a28` - Reserved for warning-related elements such as icons, labels, and notifications.
* **Red Color (Error/Danger):** `#ff6979` - Signifying error or danger, utilized for elements like icons, labels, and notifications.
* **Gray Colors:** A range of gray shades (e.g., `#666666`, `#999999`, `#CCCCCC`) serves diverse purposes, including disabled buttons, text, placeholders, and subheadings.

These color variables, thoughtfully chosen and organized, contribute to a harmonious and visually appealing design within the SB-Themes repository, offering a consistent and polished user experience.

The core color scheme in SB-Themes is established within the `:root` element, serving as the base theme colors that are loaded when the portal initializes. These meticulously chosen color variables, such as primary, secondary, tertiary, red, and various shades of gray, form the foundation of the design palette. They ensure a consistent and visually appealing user experience throughout the Sunbird-Ed portal and mobile application.

```css
:root {
  // base colors
  --blue: #024f9d;
  --green: #008840;
  --orange: #e55a28;
  --red: #ff4558;
  --indigo: #6610f2;
  --purple: #6f42c1;
  --pink: #e83e8c;
  --yellow: #ffc107;
  --teal: #20c997;
  --cyan: #17a2b8;
  --black: #000000;
  --white: #ffffff;
  --accessibility-red: #A30010;
  // gray colors shades
  --gray-hs: 0, 0%;
  --gray: hsl(var(--gray-hs), 20%);
  --gray-0: hsl(var(--gray-hs), 95%); // place holder active bg #F2F2F2
  --gray-100: hsl(var(--gray-hs), 80%); // disable btn bg, icon color #CCCCCC
  --gray-200: hsl(var(--gray-hs), 60%); // disable text, place holder text #999999
  --gray-300: hsl(var(--gray-hs), 59%); // sub heading 2 #969696
  --gray-400: hsl(var(--gray-hs), 40%); // sub heading #666666
  --gray-800: var(--gray); // text color #333333

  // basetheme
  --primary-color: #024f9d;
  --secondary-color: #008840;
  --tertiary-color: #e55a28;

  // primary colors
  --primary-0: #f3f7fa; // bg
  --primary-100: #edf4f9; // default button bg
  --primary-200: #80a7ce; // divider
  --primary-250: #d3e7f4; //pagination bg color
  --primary-300: #7ab4ee; // outline, focus fields
  --primary-400: var(--primary-color); // button bg, heading, table titles, links, toggles
  --primary-600: #005391; // on press
  --primary-800: #002e50; // hover
  --primary-color-contrast: #fff;
  --primary-color-contrast-rgb: rgb(255, 255, 255);
  --primary-color-shade: var(--primary-800);
  --primary-color-tint: var(--primary-200);

  // secondary colors
  --secondary-0: #e1ffdf; // toast bg, label
  --secondary-100: #00c786; // button bg bg, toast
  --secondary-200: #07bc81; // button bg
  --secondary-400: var(--secondary-color); // hover

  // tertiary colors
  --tertiary-0: #feedd7; // toast bg, label
  --tertiary-100: #ffa11d; // buttong bg, toast
  --tertiary-400: var(--tertiary-color); // icon, label, notification bg

  // red colors
  --red-0: #fbccd1; // toast bg
  --red-100: #ff6979; // buttong bg, toast
  --red-400: var(--red); // icon color, lable, notification
}
```

In the SB-Themes repository, the default theme is defined with precision. Key color variables within the default theme include:

* **Primary Theme Color:** `var(--primary-color)` - Serving as the primary theme color, influencing various design elements.
* **HSL and RGB Values:** `hsl(210, 97%)` and `rgb(2, 79, 156)` - Representing the HSL and RGB color notations for the primary theme color.
* **Contrast and Contrast RGB:** `#fff` and `rgb(255, 255, 255)` - Ensuring high contrast for legibility and visual appeal.
* **Shade and Tint:** `hsl(var(--primary-theme-hsl), 56%)` and `hsl(var(--primary-theme-hsl), 76%)` - Offering shading and tinting effects to create depth and dimension.

These meticulously defined color variables within the default theme contribute to a cohesive and aesthetically pleasing design, enhancing the user experience across the Sunbird-Ed portal and mobile application.

```scss
html[data-theme='default'] {
    --primary-theme: var(--primary-color);
    --primary-theme-hsl: 210, 97%;
    --primary-theme-rgb: rgb(2, 79, 156);
    --primary-theme-contrast: #fff;
    --primary-theme-contrast-rgb: rgb(255, 255, 255);
    --primary-theme-shade: hsl(var(--primary-theme-hsl), 56%);
    --primary-theme-tint: hsl(var(--primary-theme-hsl), 76%);
}
```

The visual representation of this theme inside portal comes like this

<figure><img src="../../../../.gitbook/assets/image (82).png" alt=""><figcaption><p>Landing page</p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (84).png" alt=""><figcaption><p>Modal</p></figcaption></figure>
