---
description: >-
  The Joyful Theme in SB-Themes introduces a vibrant and lively color palette
  that invigorates the visual experience. Key color variables within this theme
  include:
---

# Joyful Theme in Sunbird-Ed portal:

* **Primary Theme Color:** `#FFD954` - Utilized as the primary theme color, infusing a sense of joy and vibrancy into various design elements.
* **HSL and RGB Values:** `hsl(47, 100%, 66%)` and `rgb(255, 217, 84)` - Representing the HSL and RGB color notations for the primary theme color.
* **Contrast and Contrast RGB:** `#333` and `rgb(51, 51, 51)` - Ensuring high contrast for enhanced legibility and visual appeal.
* **Shade and Tint:** `hsl(var(--primary-theme-hsl), 56%)` and `hsl(var(--primary-theme-hsl), 76%)` - Providing shading and tinting effects for depth and dimension.

```css
html[data-color='yellow'] {
    --primary-theme: #FFD954; // hsl(47, 100%, 66%);
    --primary-theme-hsl: 47, 100%;
    --primary-theme-rgb: rgb(255, 217, 84);
    --primary-theme-contrast: #333;
    --primary-theme-contrast-rgb: rgb(51, 51, 51);
    --primary-theme-shade: hsl(var(--primary-theme-hsl), 56%);
    --primary-theme-tint: hsl(var(--primary-theme-hsl), 76%);

    --primary-color: #024f9d;
    --primary-hsl: 206, 100%;
    --primary-color-rgb: rgb(2, 79, 157);
    --primary-color-contrast: #fff;
    --primary-color-contrast-rgb: rgb(255, 255, 255);
    --primary-color-shade: var(--primary-800);
    --primary-color-tint: var(--primary-200);
    --primary-0: #f3f7fa; 
    --primary-100: #edf4f9; 
    --primary-200: #80a7ce; 
    --primary-250: #d3e7f4; 
    --primary-300: #7ab4ee; 
    --primary-400: var(--primary-color); 
    --primary-600: #005391; 
    --primary-800: #002e50;

    --sbt-body-bg: #e9e8d9;
    --sbt-body-bg2: #f3f3e5;
}

// Overriding styles for joyful theme layout sample
html[layout='joy'] {
    .sb--card {
        border-radius: 1rem !important;
        box-shadow: var(--sbt-box-shadow-6px);
    }
    .sb--card__img .img-container {
        border-radius: 0.5rem;
    }
}
```

<figure><img src="../../../../.gitbook/assets/image (85).png" alt=""><figcaption><p>Landing page</p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (86).png" alt=""><figcaption><p>Modal</p></figcaption></figure>

These color variables form the foundation of the Joyful Theme's design, creating a lively and engaging user experience.

**Dark-mode version:**

In the dark mode theme of SB-Themes, color codes are meticulously curated to ensure an appealing and user-friendly experience in low-light conditions. Let's compare these color codes with a vibrant yellow color:

* **Primary Color:** The primary color in dark mode, represented as `hsl(var(--primary-theme-hsl), 58.24%)`, exhibits a distinct contrast to the lively and energetic yellow color.
* **Shade Variations:** Shades like `--primary-0`, `--primary-100`, `--primary-200`, `--primary-250`, `--primary-300`, and `--primary-400` are tailored for dark mode, ensuring clear contrast and visibility. They stand in sharp contrast to the warm and inviting yellow hue.
* **Secondary Color:** The secondary color in dark mode, synchronized with the modified primary color, complements the theme's overall aesthetic, distinct from the radiance of yellow.
* **Gray and Text Colors:** Dark mode introduces a set of dark-themed colors (`--color-000`, `--color-111`, `--color-222`, `--color-333`, `--color-444`) for enhanced readability and visual appeal in low-light conditions.
* **Backgrounds:** Dark-themed backgrounds (`--sbt-body-bg`, `--sbt-body-bg2`) are thoughtfully chosen to create a cohesive and comfortable dark mode experience.

These purposeful color adjustments contribute to a visually engaging and user-centric dark mode theme, offering users an enjoyable experience when navigating the Sunbird-Ed portal and mobile application in reduced lighting scenarios.

```scss
html[data-mode='darkmode'] {
    // --primary-theme: var(--primary-theme);
    // --primary-theme-hsl: 49.3, 100%;
    --primary-color: hsl(var(--primary-theme-hsl), 58.24%);
    --primary-0: hsl(var(--primary-theme-hsl), 88%); // #fffcee;
    --primary-100: hsl(var(--primary-theme-hsl), 82%); // #fff8db; // default button bg
    --primary-200: hsl(var(--primary-theme-hsl), 76%); // #fffd2a; // divider
    --primary-250: hsl(var(--primary-theme-hsl), 70%); // #f1f1c7;
    --primary-300: hsl(var(--primary-theme-hsl), 64%); // #ffeb2a; // outline, focus fields
    --primary-400: var(--primary-color); // button bg, heading, table titles, links, toggles
    --primary-600: hsl(var(--primary-theme-hsl), 52%); // #ffc72a; // on press
    --primary-800: hsl(var(--primary-theme-hsl), 46%); //  #ffb62a; // hover
    --secondary-200: var(--primary-color);
    --secondary-color: var(--primary-color);
    --gray-800: var(--white);
    --color-000: #000000;
    --color-111: #111111;
    --color-222: #222222;
    --color-333: #333333;
    --color-444: #444444;
    --sbt-body-bg: var(--color-000);
    --sbt-body-bg2: var(--color-333) !important;
}
```

<figure><img src="../../../../.gitbook/assets/image (87).png" alt=""><figcaption><p>Landing page</p></figcaption></figure>

<figure><img src="../../../../.gitbook/assets/image (88).png" alt=""><figcaption><p>Modal</p></figcaption></figure>
