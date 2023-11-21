# Common Consumption Components

Contains common UI components powered by angular. These components are designed to be used in sunbird consumption platforms _(mobile app, web portal, offline desktop app)_ to drive reusability, maintainability hence reducing the redundant development effort significantly.

#### Video on Common Consumption Components

{% embed url="https://youtu.be/Q35VOcjSygs?si=TnJyE2PjyNHvXBYb&t=132" %}

{% hint style="info" %}
[https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents](https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents)
{% endhint %}

| Criteria                       | Info                                                                                                                                         |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| Current Release Branch         | v9\_Migration\_Branch                                                                                                                        |
| NPM Published version (Latest) | 4.5.2                                                                                                                                        |
| NPM Package Name               | @project-sunbird/common-consumption-v9                                                                                                       |
| NPM Link                       | [https://www.npmjs.com/package/@project-sunbird/common-consumption-v9](https://www.npmjs.com/package/@project-sunbird/common-consumption-v9) |
| Works                          | In Angular Projects Only                                                                                                                     |

### Available components

\\

<table><thead><tr><th width="277.6802931818184">Component</th><th width="492.3745047576705">Code</th></tr></thead><tbody><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/card/library-card/library-card.md">LibraryCard</a> <strong>(sb-library-card-v2)</strong></p><p>Basic Card to represent a content/asset/collection</p></td><td><em><code>&#x3C;sb-library-card-v2>&#x3C;sb-library-card-v2></code></em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/card/course-card/course-card.md">CourseCard</a> <strong>(sb-course-card)</strong></p><p>Can be used in the courses page to represent course distinctively</p></td><td><em><code>&#x3C;sb-course-card>&#x3C;sb-course-card></code></em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/card/my-course-card/my-course-card.md">MyCourseCard</a> <strong>(sb-my-course-card)</strong></p><p>Can be used in the My courses section for all consumption platforms</p></td><td><em><code>&#x3C;sb-my-course-card>&#x3C;/sb-my-course-card></code></em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/card/toc-card/toc-card.md">TocCard</a> <strong>(sb-toc-card)</strong></p><p>Can be used to represent a content in a collection.</p></td><td>NA</td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/layout/library-cards-grid/library-cards-grid.md">LibraryCardsGrid</a> <strong>(sb-library-cards-grid)</strong></p><p>Can be used represent list of collection for all consumption platforms</p></td><td><em><code>&#x3C;sb-library-cards-grid [title]="Grid Title" [isLoading]="isLoading[maxCardCount="3">&#x3C;sb-library-cards-grid></code></em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/layout/course-cards-hlist/course-cards-hlist.md">CourseCardsGrid</a> <strong>(sb-course-cards-hlist)</strong></p><p>Can be used represent list of courses for all consumption platforms</p></td><td><em><code>&#x3C;sb-course-cards-hlist [multiRow]="true" [contentList]="range(15)"[type="'curiculum_course_card_grid'" [title]="'Courses'" [isLoading]="isLoading">&#x3C;sb-course-cards-hlist></code></em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/layout/library-cards-stack/library-cards-stack.md">LibraryCardsStack</a> <strong>(sb-library-cards-stack)</strong></p><p>Can be used represent Stack of collections for all consumption platforms</p></td><td><em><code>&#x3C;sb-library-cards-stack [title]="Stack Title"[contentList]="range(15)" [maxCardCount]="3" [isLoading]="isLoading">&#x3C;/sb-library-cards-stack></code></em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/library-filters/library-filters/library-filters.md">LibraryFilters</a> <strong>(sb-library-filters)</strong></p><p>Used to construct filters based on facets</p></td><td></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/faq/faq/faq.md">FAQ Component</a> <strong>(sb-faq)</strong></p><p>Faq Section for Consumption Clients with intractable events. This is form configuration driven.</p></td><td></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/card/card-hover/card-hover.md">Card hover component</a> <strong>(sb-card-hover)</strong></p><p>Can be used with library card to add overlay on card with action items</p></td><td></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/content-details/toc-item/toc-item.md">TOCItem component</a> <strong>(sb-toc-item)</strong></p><p>shows given array of Items with accordion structure.</p></td><td></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/content-details/toc-child-item/toc-child-item.md">TOCChildItem component</a> <strong>(sb-toc-item)</strong></p><p>Shows given array of Items with accordion structure.</p></td><td></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/card/member-card/member-card.md">Member Card component</a> <strong>(sb-member-card)</strong></p><p>Member Card With Menu.</p></td><td><em><code>&#x3C;sb-member-card>&#x3C;/sb-member-card></code></em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/layout/member-list/member-list.md">Member List component</a> <strong>(sb-member-list)</strong></p><p>Member List With Cards.</p></td><td><em><code>&#x3C;sb-member-list [layoutConfig]="{size:'medium', isBold:false, isSelectable:true,view:'horizontal'}" [memberList]="range(15)" [isMenu]="false"(cardClick)="memberCardClick`` ($event)" (menuClick)="menuClick($event)">&#x3C;/</code>sb-member-list>`</em></td></tr><tr><td><p><a href="https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents/blob/v9_Migration_Branch/projects/common-consumption/src/lib/card/group-card/group-card.md">Group Card component</a> <strong>(sb-group-card)</strong></p><p>Group Card.</p></td><td><em><code>&#x3C;sb-group-card>&#x3C;/sb-group-card></code></em></td></tr></tbody></table>

## Getting Started

For help getting started with a new Angular app, check out the Angular CLI. For existing apps, follow these steps to begin using .

### Step 1: Install the package

```
npm install @project-sunbird/common-consumption --save
npm install @project-sunbird/sb-styles --save
```

### Step 2: Include the sb-styles and assets in angular.json

```
"styles": [

...

...

"./node_modules/@project-sunbird/sb-styles/assets/_styles.scss"

]
```

Add following under architect.build.assets

```
 {
    ...
    "build": {
    
    "builder": "@angular-devkit/build-angular:browser",
    
    "options": {
    
	    ...
	    ...

	    "assets": [
		   ...
		   ...
		    {
			    "glob": "**/*.*",
			    "input": "./node_modules/@project-sunbird/common-consumption/assets",
			    "output": "./assets/common-consumption"
		    }
	    ],
    "styles": [
    ...
    
    "./node_modules/@project-sunbird/sb-styles/assets/_styles.scss"
    
    ],
    
    ...
    ...

},
```

### Step 3: Import the modules and components

Import the NgModule for each component you want to use:

```
import { CommonConsumptionModule} from '@project-sunbird/common-consumption';

@NgModule({
    ...
    
    imports: [CommonConsumptionModule],
    
    ...
})
export class TestAppModule { }
```

Alternatively, you can create a separate NgModule that imports and then re-exports all of the Angular components that you will use in your application. By exporting them again, other modules can simply include your CustomSunbirdComponentsModule wherever components are needed, and automatically get all of the exported modules. A good place for importing/exporting the application-wide modules is the SharedModule.

```
import { CardsModule } from '@project-sunbird/common-consumption/card';

import { PopoverModule } from '@project-sunbird/common-consumption/popover';

@NgModule({

...

imports: [CardsModule, PopoverModule],

exports: [CardsModule, PopoverModule],

...

})


export class MyOwnCustomSunbirdComponentsModule { }
```

For More Information, Please refer to GitHub repo link.
