# Cards

Cards play a pivotal role in the Sunbird-Ed portal's design, facilitating organized content presentation. What sets our approach apart is the use of pure HTML and SCSS, ensuring a structured and modular development process. This approach simplifies customization while maintaining consistency with our style guide.

Moreover, we've implemented theme-specific card styles to cater to diverse user preferences. Whether it's the vibrant Joy theme or its darker counterpart, each theme comes with distinct card styling, offering a visually harmonious and immersive user experience.

**Key Features:**

* **Responsiveness:** Our cards are designed to adapt seamlessly to various screen sizes and devices, ensuring a user-friendly experience.
* **Consistency:** A standardized card structure simplifies navigation and access to content throughout the portal.
* **Customization:** While adhering to our style guide, we've built flexibility into our card design, enabling users to tailor card styles according to their specific branding and content needs.
* **Enhanced Content Presentation:** Cards are instrumental in making information more digestible and visually appealing, enhancing the overall user experience.

In summary, our use of cards in the Sunbird-Ed portal combines functional design with adaptability and aesthetics, all while offering customization options that align with user preferences and branding requirements. For more information please refer to this link [https://sunbird-ed.github.io/sunbird-style-guide/dist/#/cards](https://sunbird-ed.github.io/sunbird-style-guide/dist/#/cards)

**Variations:**

**Card Type-1 for Default theme:**

<figure><img src="../../../../../.gitbook/assets/image (73).png" alt=""><figcaption></figcaption></figure>

```html
<div class="sb-card" tabindex="0">
  <div class="sb-card-body">
    <div class="sb-card-metas">
      <div class="sb-card-image mr-16"><img src="assets/images/book.png"></div>
      <div class="sb-card-meta non-course">
        <div class="d-flex mb-auto">
          <div class="sb-card-label">Worksheet</div>
          <img src="assets/images/badge1.png" class="sb-card-badge ml-auto">
        </div>
        <div class="sb-card-meta-item ellipsis">Subject : English</div>
        <div class="sb-card-meta-item ellipsis mt-4">
          Class : Class 1,Class 2,Class 3,Class 4,Class 5
        </div>
        <div class="sb-card-meta-item ellipsis mt-4"> Medium : Other</div>
      </div>
    </div>
    <h4 class="sb-card-title"> Structure and Algorithm - Assignment 1 Paperback
    </h4>
    <div class="sb-card-org ellipsis">Academy of European Law (ERA)
    </div>
  </div>
  <div class="sb-card-progressbar">/div>
</div>
```

**Card Type-2 for Default Theme:**

<figure><img src="../../../../../.gitbook/assets/image (75).png" alt=""><figcaption></figcaption></figure>

```html
<div class="sb--card mb-16" tabindex="0" role="button">
        <div class="sb--card__main-area">
            <!-- card img -->
            <div class="sb--card__img">
                <div class="img-container"><img alt="" src="https://material.angular.io/assets/img/examples/shiba2.jpg"></div>
            </div>
            <!-- card mobile view details -->
            <div class="sb--card__info">
                <div class="sb--card__meta1">
                    <h4 class="sb--card__title sb__ellipsis sb__ellipsis--two text-left flex-basis-1" title="Title comes here">
                    Title comes here</h4>
                    <a aria-label="View more actions" class="menu" role="button" tabindex="0"></a>
                </div>  
        
                <div class="sb--card__meta1 text-left">
                    <span class="data_1 ellipsis" title="subject comes here">dsubject comes here</span>
                    <span class="dot-divider"></span>
                    <span class="data_2 ellipsis" title="grade level comes here">grade level comes here</span>
                </div>
            </div>
        </div>
        <div class="sb--card__moreinfo">
            <div class="sb--card__meta2 text-left">
                <div class="sb--card__meta2_data">Medium: medium</div>
                <div class="sb--card__org sb__ellipsis">organisation</div>
            </div>
            <div class="sb--card__tags">
                <span class="sb--card__badge"><img alt="" title=""
                        src="https://material.angular.io/assets/img/examples/shiba2.jpg"></span>
                <span class="sb--card__type">resourceType</span>
            </div>
        </div>
    </div>
```

**Card Type-3 for Joy Theme:**

<figure><img src="../../../../../.gitbook/assets/image (76).png" alt=""><figcaption></figcaption></figure>

{% code overflow="wrap" %}
```html
<div class="sb--card sb--card--theme2" role="link" tabindex="0">
      <svg width="79px" class="sb--card-svg-tail" height="36px" viewBox="0 0 79 36" version="1.1"
        xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
          <g class="sb--card-svg-tail__rc" transform="translate(-735.000000, -524.000000)">
            <g transform="translate(517.000000, 338.000000)">
              <g>
                <path
                  d="M224.269945,224.907985 C224.269945,224.907985 217.096964,205.264724 219.487958,199.23369 C221.878951,193.203161 229.905965,205.609232 231.442925,210.261729 C231.442925,210.261729 230.930605,187 237.762123,187 C244.59339,187 245.447423,217.498667 245.447423,217.498667 C245.447423,217.498667 247.838417,203.54168 252.27894,203.54168 C256.719214,203.54168 251.424907,219.049331 253.645044,218.704823 C255.865431,218.360315 264.612662,211.290301 270.931859,218.871747 C277.250806,226.453445 274.347493,238.1705 281.17901,237.998119 C288.010277,237.825992 268.503575,211.123125 272.431528,205.95374 C276.359732,200.784607 286.265169,212.84617 287.119203,215.94775 C287.119203,215.94775 286.606883,199.23369 291.218013,199.23369 C295.829393,199.23369 296,223.18494 296,223.18494 L224.269945,224.907985 Z">
                </path>
              </g>
            </g>
          </g>
        </g>
      </svg>
      <div class="sb--card__main-area">
        <!-- card img -->
        <div class="sb--card__img sb--card__image-pos">
          <div class="img-container">
            <img src="https://material.angular.io/assets/img/examples/shiba2.jpg" alt="">
          </div>
        </div>
        <div class="sb--card__svg-area">
          <img src="https://staging.sunbirded.org/assets/common-consumption/images/abstract_02.svg" alt=""/>
        </div>
        <div class="sb--card__type">Card type</div>
      </div>
    
      <!-- card mobile view details -->
      <div class="sb--card__info">
        <div class="sb--card__meta">
          <h4 class="sb--card__title sb__ellipsis sb__ellipsis--two text-left flex-basis-1" title="">
            Content Name</h4>
        </div>
        <div class="sb--card__meta1 text-left">
            <span class="data_0 mr-8 organisation" title="">organisation</span>
            <span class="data_0 mr-8" title="">+11</span>
    
            <span class="data_1 mr-8 medium" title="">Medium</span>
            <span class="data_1 mr-8" title="">+3</span>
    
            <span class="data_2" title="">Grade level</span>
            <span class="data_2" title="">+4</span>
        </div>
      </div>
      <!-- content for only desktop -->
      <div>
        <div class="sb--card__moreinfo">
          <!-- other meta info subject, publisher/organizer etc -->
          <div class="sb--card__meta2 text-left">
              <div class="sb--card__meta2_data sb__ellipsis subject">
                <span>Subject: </span> <span title="">Telugu</span> <span class="data_1 mr-8" title=""> +5
                </span>
              </div>
              <div class="sb--card__meta2_data sb__ellipsis organisation">
                <span>Publisher: </span> <span title="">Org</span>
                <span class="data_1 mr-8" title=""> +6
                </span>
              </div>
          </div>
          </div>
        </div>
      </div>
    </div>
```
{% endcode %}
