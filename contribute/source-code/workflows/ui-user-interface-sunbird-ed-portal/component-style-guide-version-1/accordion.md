# Accordion

**Accordion Component Overview:**&#x20;

Our portal features a functional Semantic Accordion for organized content presentation.&#x20;

**Key Features:**

* Expandable sections simplify content access.
* User-friendly interface enhances navigation.
* Customizable to match the portal's design.
* Prioritizes accessibility for all users.
* Enhances the overall user experience.

This provides a concise overview of the Semantic Accordion's role and benefits in the Sunbird-Ed portal.&#x20;

For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/accordion](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/accordion)

**Example:**

<figure><img src="../../../../../.gitbook/assets/image (63).png" alt=""><figcaption></figcaption></figure>

```html
<sui-accordion class="sb-accordion">
  <sui-accordion-panel [isOpen]="true">
    <div title class="sb-accordion-title">
      Why am I unable to sign up?
      <i class="chevron down icon right-floated d-flex flex-ai-center"></i>
    </div>
    <div content class="sb-accordion-content">
      <p class="sb-accordion-text">The Sign In feature allows authorized users to access content using the app. Using
        this feature, it is possible to differentiate content for different user types. For example, anonymous or guest
        users can view only a limited number of courses and resources, while registered users have access to all content
        available in the Library.</p>
    </div>
    <div content class="sb-accordion-footer d-flex flex-ai-center flex-jc-center flex-dc">
      <div class="m-0">Did this answer help you?</div>
      <div class="mt-8">
        <button type="button" class="sb-btn sb-btn-normal sb-btn-link sb-btn-link-primary mr-8">No</button>
        <button type="button" class="sb-btn sb-btn-normal sb-btn-link sb-btn-link-secondary">Yes</button>
      </div>
      <div class="sb-label sb-label-table sb-label-success-0 mt-8">Thanks for your response!</div>
    </div>
  </sui-accordion-panel>
  <sui-accordion-panel>
    <div title class="sb-accordion-title">
      Why can’t I find my class?
      <i class="chevron down icon right-floated d-flex flex-ai-center"></i>
    </div>
    <div content class="sb-accordion-content">
      <p class="sb-accordion-text">The Sign In feature allows authorized users to access content using the app. Using
        this feature, it is possible to differentiate content for different user types. For example, anonymous or guest
        users can view only a limited number of courses and resources, while registered users have access to all content
        available in the Library.</p>
    </div>
    <div content class="sb-accordion-footer">
      <div class="sb-help-section-subheading">Sorry about that</div>
      <div class="sb-help-section-extra mt-8">What more would you like to know?</div>
      <div class="sb-field-group mt-16">
        <div class="sb-field">
          <textarea rows="4" class="sb-form-control" placeholder="Type here"></textarea>
        </div>
      </div>
      <button type="button" class="sb-btn sb-btn-primary sb-btn-normal d-flex ml-auto">Submit</button>
    </div>
  </sui-accordion-panel>
</sui-accordion>
```
