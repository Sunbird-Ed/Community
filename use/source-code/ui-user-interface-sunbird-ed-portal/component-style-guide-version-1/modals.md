# Modals

Our portal features user-friendly modals that seamlessly integrate into the design. These modals enhance user interactions, provide consistency, and allow for customization to meet specific needs. For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/modals](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/modals)

**Modal in Default theme:**

<figure><img src="../../../../.gitbook/assets/image (34).png" alt=""><figcaption></figcaption></figure>

**Modal in Joyful theme:**

<figure><img src="../../../../.gitbook/assets/image (33).png" alt=""><figcaption></figcaption></figure>

```html
<sui-modal *ngIf="showNormalModal" [mustScroll]="true" [isClosable]="true" [transitionDuration]="0" [size]="'normal'"
  class="sb-modal" appBodyScroll (dismissed)="showNormalModal = !showNormalModal" #modal>
  <div class="sb-modal-header">
    Modal Heading
  </div>
  <div class="sb-modal-content">
    Modal Content
  </div>
  <div class="sb-modal-actions">
    <button class="sb-btn sb-btn-normal sb-btn-primary" (click)="doSomething()">
      Yes
    </button>
    <button class="sb-btn sb-btn-normal sb-btn-outline-primary" (click)="doSomething()">
      No
    </button>
  </div>
</sui-modal>
```
