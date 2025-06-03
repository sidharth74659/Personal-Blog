- [ ] What should we call it: _dynamicForms_, _digitalForms_, _smartForms_?
- [ ] add _.angular_, _.vscode_ to _.gitignore_
- [ ] Maintain a guides folder containing(for users and developer overview):
   - [ ] **routes.md**: table of routes, nested routes and what they are for
   - [ ] **features.md**
   - [ ] **design-system.md**: design-system, variables, typography, etc.
- [ ] please refer [pr-checklist.md](https://bitbucket.org/mobilesupplychain24c/propel-guide/src/main/pr-checklist.md "https://bitbucket.org/mobilesupplychain24c/propel-guide/src/main/pr-checklist.md")

- [ ] If _subscribing_, then _unsubscribe_. Ex: _src/app/components/component-palette/component-palette.component.ts_
- [ ] css-classes should be hyphen-separated and descriptive. Ex: `applyBtn` -> `apply-btn`, `componentProperties` -> `component-properties`, `fcsettings` -> `form-control-settings`.
- [ ] file-names should be in kebab-case. Ex: `create new form.png` -> `create-new-form.png`
	- [ ] On the same note, shouldn't be a component instead of using a `.png` for displaying *create-new-form*?

- [ ] **Folder Structure:**

   - [ ] maintain a clear-distinction b/w pages, sections and unit-level components. Meaning:

      - [ ] the project-view and form-view is a page
      - [ ] _component-palette_, _form-canvas_ is something of a selection which groups a set of components
      - [ ] _button_, _radio_ are something that are of unit-level components that gets re-used and has its own styling and structure.

- [ ] **Logging:**

   - [ ] reserve _.info_ logs only for the places where it should be(do not use it for _log_ or _verbose_ purpose)
   - [ ] simple rule: don't add anything you would not want to see in a website's console
   - [ ] also, have a _business-config_ within logger-service which would prevent logging(by early return)
   - [ ] avoid excessive or unnecessary logging. For ex:

   ```js
   // not required to log this
   this.componentSettings = settings;
   this.logger.info("Component settings loaded:", settings);

   // the else case here doesn't serve a purpose
   if (settings) {
     this.syncComponentSettings();
   } else {
     this.logger.warn(
       `No settings found for component type: ${this.selectedComponent?.type}`
     );
   }


    // another example for excessive logging.
	// Also, else-case doesn't serve a purpose here. consider if it supposed to be a toast-message. and also .error() should be used in catch-block not for normal flow.
		this.formComponentsChange.emit([...this.formComponents]);
		this.formTagsChange.emit([...this.formTags]);

		this.logger.info('Form template loaded successfully');
		this.logger.info('Template status:', this.templateStatus);
		this.logger.info('Is draft:', this.isDraft);
	} else {
		this.logger.error('Failed to load form template');
	}

   ```

   - [ ] **_Remember:_** When using _.warn_ or _.info_, consider if this is something that needs to be shown via toast-message, if not -> make it as a _.debug_ log(so we can avoid logging based on _business-config_ in production)

- [ ] in constructor, keep the key and value name to be same. Ex: `private loggerService: LoggerService`
	- [ ] use `private` instead of `public`, and use appropriately. I've seen many places where `protected` is used without a purpose.
- [ ] **remove any unused classes, styles or code**.
   - [ ] Ex: `applyBtn` in _component-properties/component-properties.component.html_
- [ ] For every _component_, have a main-container that is same as the file-name, and use that within the respective _.scss_ file for additional specificity. Let me know if you have any doubts in that.

   ```scss
   // in component-properties.component.html
   <div class="form-canvas">
   <div class="canvas-heading">
   	<!-- content -->
   </div>
   </div>
   
   // in component-properties.component.scss
   .form-canvas {
     .canvas-heading {
       // styles
     }

     .canvas-title {
       // styles
     }
   }
   ```

- [ ] **Component-based platform:**

    - [ ] there should not be any button styles within another-page, a component should be used instead

    ```js
    <!-- Example: avoid using the following thing within other components -->
    <button type="button" class="cancel-btn" (click)="cancel()">Cancel</button>
    <button type="button" class="btn publish-btn create-btn" (click)="publishForm()">Submit</button>
    <!-- Also, a note, it should be 'submitForm', not 'publishForm' -->

    <!-- Instead, do this -->
    <form-button [text]="Cancel" [type]="cancel" (onClick)="cancel()">
    <form-button [text]="Submit" [type]="create" (onClick)="submitForm()">
    ```

- [ ] **Naming Convention:** should be clear and understandable, instead of generic.

    - [ ] Ex: here(in the screenshot) if the _displayTab_ field is for the label, rename it to: _displayTabLabel_
       ![[Pasted image 20250509221032.png]]
    - [ ] _radioOptions, allSettings, connectedDropLists,_ etc*:* be more specific and use interface
    - [ ] _⁠uniqueKeyManuallyEdited_: booleans should be a verb
    - [ ] similarly for method names. Ex: _generateCellConnections_ doesn't explain what it does. `initializeRadioOptions` -> `loadRadioOptions`
    - [ ] use types(if local, then within that file, if also used elsewhere, then into a file) instead of { [key: string]: ... }, make that into a type prefixed with 'T'
    - [ ] avoid vague naming for css-classes like: `middle-content-area`, be more specific and understandable. What exactly does `orange-txt` mean?
    - [ ] constants should be in `constants.ts` file and should be in capital letters. Ex: `FormTemplateStatus` -> `FORM_TEMPLATE_STATUS`
    - [ ] Please get familiar with **BEM Convention** for css-classes.
    - [ ] Keep the naming consistent.

    ```js
    // in button-field/button-field.component.ts
    onButtonClick(event: Event) {
    	...
    }

    // prefer using `onRemoveElement` or `onRemoveClick` instead of `remove`
    remove() {
    	...
    }
    ```
	- [ ] Proper file-names: instead of `FormElementsService`(if it is an api-service), then `FormElementsApiService`(similarly `form-elements.service.ts` -> `form-elements.api.service.ts`).
		- [ ] And group similar files in a folder. Ex: `form-elements.api.service.ts`,  `form-storage.service.ts` into a folder

- [ ] **Comments:**

    - [ ] purpose should be clear, not for describing everything(the code should do that) unless its complex. Ex: avoid following type of comments where it doesn't specify what it does

    ```js
      <!-- unnecessary comment and method-name doesn't clarify the functionality -->
      // Add this method to your component
      private generateCellConnections(): void {


    <!-- when the code is clear and is self-explainatory, no need of comment -->
    // Initialize table settings if applicable
      if (this.selectedComponent?.type === 'fixedtable') {
        this.initializeTableSettings();
      }

    <!-- Maintain consistency in comments, do not use out of pattern symbols like: -->
    // <-- Emit when user clicks cancel

    ```

    - [ ] check the difference b/w JsDoc and comments, and accordingly use the right one where it fits.
    - [ ] For complex methods or most-used common methods, include _usage_ and _@example_ as well including inputs and outputs

- [ ] Maintaining abstraction:
    - [ ] The usual standard for maintaining components is:
       - [ ] `component.html` should be for semantic and component-based
       - [ ] `component.scss` for the component-specific styling
       - [ ] `component.ts` for component-specific logic that is to be abstracted
       - [ ] `component.service.ts` for logic that should not be in _component-specific logic_
    - [ ] Any additional logic or calculation should be moved to either component-specific `.service` file or if shared-logic then to a shared-service file, thus making it easier to maintain.
    - [ ] One way to maintain is to limit the number of lines in .html, .scss, .ts in `angular.json`, which enforces you to keep things separated. Please look into more on this and implement it.
    - [ ] One example is `src/app/components/component-properties/component-properties.component.ts` is no-way need to have **`1441`** lines. If we're exceeding specific lines, it means the implementation/approach is something that needs to be improved.
- [ ] **Typescript**:

    - [ ] interfaces should always be prefixed with `I` and types with `T`
    - [ ] Default values should not be specified, and if needed, should be provided a default-value.

    ```typescript
    <!-- Instead of this -->
      updatedById?: string;
      createdById?: string;
      defaultValue?: string;

    <!-- Do this -->
      updatedById: string = '';
      createdById: string = '';
      defaultValue: string = '';

    <!-- or -->

    updatedById: string | undefined;
    createdById: string | undefined;
    defaultValue: string | undefined;
    ```

    - [ ] Avoid using `any` type. Ex: check for `field` property in `button-field/button-field.component.ts`

- [ ] **Common Code**

    - [ ] There should be a common-files for most basic and most used code.
      - [ ] which allows you to implement any common implementation in a single place(like _encryption_).
    - [ ] For examples, for setting and getting data from local-storage, there should be a `local-storage.service.ts` file(and should be async, so that if it is used in async way in future(like using another plugin or package), it should be awaited).

- [ ] Order of placement:

    - [ ] In any `.component.scss`, keep the order of placement as:
      - [ ] imports
      - [ ] any variables like `$label-width: 30%;` or `--text-color: #333;`
      - [ ] continue with the styles

- [ ] Leverage `.scss`:
	```scss
	// instead of:
	.form-group .form-control {
		border-radius: 0px;
	}

	.form-group .form-label {
		padding: 0px;
	}

	// do this:
	.form-group {
		.form-control {
			border-radius: 0px;
		}

		.form-label {
			padding: 0px;
		}
	}
	```

**Additional things:**

- [ ] Missing global-styles folder containing design-system, variables, typography, etc. which is concerning.
- [ ] Setup a business-config that is of getter and setter approach and within a service file, but should be exposed as a direct import instead of a service.
- [ ] Avoid using `any` type.
- [ ] Use only svg icons instead of png and with clear-names. Ex: `forms-data-blue`, `forms-list-white` are not good names.
	- [ ] look for spelling mistakes in the code or file-names. Ex: `delet.svg` -> `delete.svg`
	- [ ] avoid redundant files or icons. Ex: `link.png`, `url.svg` and `edit-png`, `edit.svg`
	- [ ] set file-names in a way that would be grouped(by title). Ex: instead of `up-arrow.svg`, `down-arrow.svg` -> `arrow-up.svg`, `arrow-down.svg`
- [ ] update `favicon.ico`
- [ ] shared-service
- [ ] implementtranslation
- [ ] use *enums* where something can be served as a value and an interface and is usually a group. Ex: 