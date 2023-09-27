# Tabs

Tabs serve as an effective navigation and organization tool within the Sunbird-Ed portal. They allow users to switch between different sections or views with ease, enhancing the user experience and facilitating content exploration. For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/tabs](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/tabs)

<figure><img src="../../../../../.gitbook/assets/image (46).png" alt=""><figcaption></figcaption></figure>

```
<sui-tabset>
  <div class="ui top attached tabular menu">
    <a class="item" suiTabHeader="1">First</a>
    <a class="item" suiTabHeader="2">Second</a>
    <a class="item" suiTabHeader="3">Third</a>
  </div>
  <div class="ui bottom attached segment" suiTabContent="1">First tab!</div>
  <div class="ui bottom attached segment" suiTabContent="2">Second tab!</div>
  <div class="ui bottom attached segment" suiTabContent="3">Third tab!</div>
</sui-tabset>
```

<figure><img src="../../../../../.gitbook/assets/image (47).png" alt=""><figcaption></figcaption></figure>

```html
<sui-tabset>
  <div class="ui pointing secondary menu">
      <a class="item" suiTabHeader="1">Nested 1</a>
      <a class="item" suiTabHeader="2">Nested 2</a>
  </div>
  <div class="ui segment" suiTabContent="1">First nested tab!</div>
  <div class="ui segment" suiTabContent="2">Second nested tab!</div>
</sui-tabset>
```
