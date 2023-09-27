# SunbirdEd Forms

Contains Form component powered by angular. This component expects a configuration and renders form according to the view.

{% hint style="info" %}
[https://github.com/Sunbird-Ed/SunbirdEd-forms](https://github.com/Sunbird-Ed/SunbirdEd-forms)
{% endhint %}

| Criteria                       | Info                                                                                                                       |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| Current Release Branch         | release-4.4.0                                                                                                              |
| NPM Published version (Latest) | 0.0.14                                                                                                                     |
| NPM Package Name               | @project-sunbird/form-service                                                                                              |
| NPM Link                       | [https://www.npmjs.com/package/@project-sunbird/form-service](https://www.npmjs.com/package/@project-sunbird/form-service) |
| Works                          | In Angular Projects Only                                                                                                   |

## Getting Started

### Step 1: Install the package

```
npm install common-form-elements --save
```

### Step 2: Include the library selector in view( Eg .HTML file)

\<sb-form \[config]='config'>

### step3: Form component emits values on every input , To get value include event callbacks

```
<sb-form (valueChanges)="function($event)" (statusChanges)="function($event)" >
```



### Steps to Integrate the form

Please refer following link for sample config

[https://github.com/Sunbird-Ed/SunbirdEd-forms/blob/release-4.1.0/projects/common-form-elements/src/lib/form/form.component.ts](https://github.com/Sunbird-Ed/SunbirdEd-forms/blob/release-4.1.0/projects/common-form-elements/src/lib/form/form.component.ts)

The Form Can render following elements:

* Text Box
* Text Area
* Drop Down (Single)
* Multi Select Drop Down

Drop Down Data Sources: Drop Down can be provided with multiple types of Data Sources:

* Static List
* Closure which is called as MARKER in above config (A function which returns Promise of FieldConfig)
* API Source - Currently Not Developed (Open For Contribution)

Example of Closure Implementation

```
buildStateListClosure(config: FieldConfig<any>, initial = false): FieldConfigOptionsBuilder<Location> {
    return (formControl: FormControl, _: FormControl, notifyLoading, notifyLoaded) => {
      return defer(async () => {
        const req: LocationSearchCriteria = {
          from: CachedItemRequestSourceFrom.SERVER,
          filters: {
            type: LocationType.TYPE_STATE
          }
        };
        notifyLoading();
        return this.fetchUserLocation(req)
          .then((stateLocationList: Location[]) => {
            notifyLoaded();
            const list = stateLocationList.map((s) => ({ label: s.name, value: s }));
            if (config.default && initial) {
              const option = list.find((o) => o.value.id === config.default.id || o.label === config.default.name);
              formControl.patchValue(option ? option.value : null, { emitModelToViewChange: false });
              formControl.markAsPristine();
              config.default['code'] = option ? option.value['code'] : config.default['code'];
            }
            initial = false;
            return list;
          })
          .catch((e) => {
            notifyLoaded();
            this.commonUtilService.showToast('NO_DATA_FOUND');
            console.error(e);
            return [];
          });
      });
    };
  }
```

The Logic Inside can be customised to own needs of project.

Function Signature should be as follows:

```
functionName(config: FieldConfig<any>, initial = false): FieldConfigOptionsBuilder<T>
```
