# SB-Themes Repository: Unifying Design Across Platforms

The SB-Themes repository serves as a standalone repository that plays a pivotal role in both the Sunbird-Ed portal and the Sunbird-Ed mobile application. It embodies a unified design philosophy that ensures a consistent visual identity across these platforms.

**Themes for Sunbird-Ed Portal:**

Within the portal, SB-Themes introduces two distinct themes, each with its corresponding dark mode version:

1. **Classical Theme:** This theme offers a timeless and conventional visual style, catering to users who prefer a classic aesthetic.
2. **Joyful Theme:** In contrast, the Joyful theme brings vibrancy and energy to the portal's design, creating a visually engaging and joyful user experience.

**Dynamic Theme Switching:**

The magic lies in the use of CSS3 variables, which enable dynamic theme switching. When transitioning from one theme to another, structural changes occur throughout the portal.

This includes adjustments to the layout, button styles, card designs, modals, select boxes, and more. These changes align seamlessly with the chosen theme, ensuring a cohesive and visually pleasing user interface.

**Consistency Across Platforms:**

The same design philosophy extends to the Sunbird-Ed mobile application, ensuring that users experience a harmonious and familiar visual environment regardless of the device they use.

In summary, SB-Themes offers a versatile and efficient approach to theming, enhancing the user experience by providing choices and maintaining design consistency across both the Sunbird-Ed portal and mobile application. To add the `sb-themes` GitHub repository as a dependency in your portal's `package.json` file, you can use the following command:

```bash
npm install @project-sunbird/sb-themes --save
```

This will fetch the `sb-themes` repository and add it as a dependency in your project's `package.json` file, allowing you to use it in your portal.

<figure><img src="../../../../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

When you install the `@project-sunbird/sb-themes` package using npm, it will be added as a dependency in your project's `package.json` file. The folder structure of your project will remain largely the same, but you will have the `sb-themes` package available in your `node_modules` directory. Here's how the structure may look:

```lua
your-project/
|-- node_modules/
|   |-- @project-sunbird/
|       |-- sb-themes/
|           |-- ... (Theme-related files and assets)
|-- src/
|-- package.json
|-- ...
```

In the `node_modules` directory, you will find the `sb-themes` package along with its theme-related files and assets.

You can then import and use the themes provided by `sb-themes` in your Angular project by configuring your application's styles and components to use the predefined theme styles and variables provided by the package. These themes will affect the visual appearance of your portal's UI. Folder structure&#x20;

<figure><img src="../../../../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

`sb-themes` package is used in the Sunbird-Ed portal to manage different themes and styles. `themes-portal.scss` is the central stylesheet responsible for for defining the main styles for various sections and themes in the portal.

We have defined themes for each section like darkmode, accessibility, base and joy layout etc. Here is the screenshot attached for the reference

<figure><img src="../../../../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

**Note:** "theme-mono1" and "theme-purple" themes, but these themes have not been implemented in the portal by default. Users interested in using these themes would need to make manual changes to enable and apply them in the portal.

After installing sb-themes, you'll need to link the file path within your project. For instance, in our Sunbird-ed portal project, we accomplished this by specifying the path in the angular.json configuration file.

<figure><img src="../../../../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

In addition, we utilize themes-material\_UI within the portal. These style overrides are related to the Joy theme layout and are specifically tailored to the Angular Material section.

<figure><img src="../../../../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>
