# Toast messages

Our toasts are subtle yet effective notifications, featuring color variations such as primary, success, warning, and error. These toasts provide essential feedback and information to users in a visually appealing and unobtrusive manner, enhancing their overall experience within the portal. For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/toasters](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/toasters)

<figure><img src="../../../../../.gitbook/assets/image (48).png" alt=""><figcaption></figcaption></figure>

```html
<div class="sb-toaster sb-toast-info">
  <div class="sb-toast-body">
    <i class="book icon sb-toast-icon"></i>
    <div class="sb-toast-texts">
      <div class="sb-toast-title">Simple Meassage</div>
      <div class="sb-toast-message">message comes here</div>
    </div>
    <span class="sb-toast-close-icon"></span>
  </div>
</div>
<div class="sb-toaster sb-toast-success">
  <div class="sb-toast-body">
    <div class="sb-toast-texts">
      <div class="sb-toast-title">Thank you!</div>
      <div class="sb-toast-message">We have received your download request.
       The file will be sent to your registered email ID shortly.</div>
    </div>
    <span class="sb-toast-close-icon"></span>
  </div>
</div>
<div class="sb-toaster sb-toast-warning">
  <div class="sb-toast-body">
    <i class="warning icon sb-toast-icon"></i>
    <div class="sb-toast-texts">
      <div class="sb-toast-title">Download failed!</div>
      <div class="sb-toast-message">Your profile does not have a valid email ID. Please update your email ID.</div>
    </div>
    <span class="sb-toast-close-icon"></span>
  </div>
</div>
<div class="sb-toaster sb-toast-danger">
  <div class="sb-toast-body">
    <i class="plus icon sb-toast-icon"></i>
    <div class="sb-toast-texts">
      <div class="sb-toast-title">Delete this Content Type</div>
      <div class="sb-toast-message">When you delete a folder you also delete all of its contents.</div>
    </div>
    <span class="sb-toast-close-icon"></span>
  </div>
</div>
```
