# Forms

Forms are a core component of the Sunbird-Ed portal, offering a cohesive and user-friendly experience. We've carefully designed our forms to align with our style guide, ensuring a consistent look and feel across the application.

Within our forms, we've implemented customized checkboxes and radio buttons. These elements not only maintain visual harmony with our design but also enhance user interactions. Users can engage with these form elements effortlessly, providing a seamless and intuitive experience. For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/forms](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/forms)

**Example of Checkboxes:**

<figure><img src="../../../../.gitbook/assets/image (77).png" alt=""><figcaption></figcaption></figure>

```html
<div class="d-flex flex-w-wrap">
  <div class="sb-checkbox sb-checkbox-primary">
    <input type="checkbox" id="check1" name="example">
    <label for="check1">Primary checkbox</label>
  </div>
  <div class="sb-checkbox sb-checkbox-secondary">
    <input type="checkbox" id="check2" name="example">
    <label for="check2">Secondary checkbox</label>
  </div>
  <div class="sb-checkbox sb-checkbox-warning">
    <input type="checkbox" id="check3" name="example">
    <label for="check3">Warning checkbox</label>
  </div>
  <div class="sb-checkbox sb-checkbox-error">
    <input type="checkbox" id="check4" name="example">
    <label for="check4">Error checkbox</label>
  </div>
</div>
```

**Example of Radio buttons:**

<figure><img src="../../../../.gitbook/assets/image (78).png" alt=""><figcaption></figcaption></figure>

```
<div class="d-flex flex-w-wrap">
      <div class="sb-radio-btn-checkbox sb-radio-btn-primary">
            <input type="radio" id="radio11" name="example">
            <label for="radio11">Primary checkbox</label>
      </div>
      <div class="sb-radio-btn-checkbox sb-radio-btn-secondary">
            <input type="radio" id="radio12" name="example">
            <label for="radio12">Secondary checkbox</label>
      </div>
      <div class="sb-radio-btn-checkbox sb-radio-btn-warning">
            <input type="radio" id="radio13" name="example">
            <label for="radio13">Warning checkbox</label>
      </div>
      <div class="sb-radio-btn-checkbox sb-radio-btn-error">
            <input type="radio" id="radio14" name="example">
            <label for="radio14">Error checkbox</label>
      </div>
</div>    
```

**Example of Form Fields:**

<figure><img src="../../../../.gitbook/assets/image (79).png" alt=""><figcaption></figcaption></figure>

```html
<div class="sb-field-group">
  <label>Field Name</label>
  <div class="sb-field">
    <input class="sb-form-control" type="text" placeholder="Enter Mobile Number">
    <i class="search icon sb-input-icon"></i>
  </div>
</div>
```

<figure><img src="../../../../.gitbook/assets/image (80).png" alt=""><figcaption></figcaption></figure>

```html
<div class="sb-field-group">
    <label>Field Label</label>
    <div class="sb-field relative">
        <textarea rows="4" name="moretext" class="sb-form-control" placeholder="Type here..."></textarea>
        <span class="characters-left">1000 Characters left</span>
    </div>
</div>
```
