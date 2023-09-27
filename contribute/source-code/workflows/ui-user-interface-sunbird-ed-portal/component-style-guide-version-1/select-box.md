# Select Box

Our select box component serves as a versatile tool within forms, offering both single-select and multi-select options. This flexibility enhances user interactions and ensures an intuitive experience for users when making choices or selections. For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/select](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/select)

**Example of Single Select box:**

<figure><img src="../../../../../.gitbook/assets/image (43).png" alt=""><figcaption></figcaption></figure>

```html
<sui-select class="selection" [(ngModel)]="selectedOption" [options]="options"
labelField="name" [isSearchable]="searchable" [isDisabled]="disabled" #select>
           <sui-select-option *ngFor="let option of select.filteredOptions"
                      [value]="option">
           </sui-select-option>
</sui-select>
```

**Example of Multi Select box:**

<figure><img src="../../../../../.gitbook/assets/image (44).png" alt=""><figcaption></figcaption></figure>

```html
<sui-multi-select class="selection" [(ngModel)]="selectedOptions" [options]="options"
labelField="name" [isSearchable]="searchable" [isDisabled]="disabled" [hasLabels]="!hideLabels"
#multiSelect>
     <sui-select-option *ngFor="let option of multiSelect.filteredOptions"
          [value]="option">
     </sui-select-option>
</sui-multi-select>
```
