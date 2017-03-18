# react-redux-template
Feature based approach of creating react-redux applications.
## Includes
- React
- Redux
- Babel for ES6/7 syntax support (including class properties, generators)
- Redux-saga for managing asynchronous events
- SCSS syntax support
- Webpack for handling file and module imports
- Gulp for managing build tasks (including webpack task too)
- Bluebird

## Proposed structure
- /src - application source directory
	- /components - common components which are expected to be reused by other components.
	- /constants - application constants. Consists of mirrored values and key-value pairs.
	- /data - a place for any common reducers or sagas that doesn't below directly to any component.
	- /scenes - unique root components. Think about like pages or screens of your application.
	- /scss - common directory for scss stylesheets. Should consist of common files with appropriate imports from scenes and common components.
	- /services - common directory for any services used in application.
- build - application output directory.
	- js - javascript files output directory.
	- css - css files output directory.
	- images - any images being imported by components.
	
## Component structure example
- /ExampleComponentName - component root directory
	- /components - child components that only belong to ExampleComponentName.
	 	- ChildComponent - child component which follows the same structure. Child components could only be used by any parent components, but not by sibling one.
	 	- ...
	- /images - any images required by ExampleComponentName and loaded via require/import.
	- _example-component-name.scss - component styles.
	- presenter.js / container.js - component file itself. Depending on component role and ability to manage application state it could be a presenter or a container.
	- index.js - default export file.
	- reducer.js - component reducer (for container component).
	- actions.js - component actions to interact with application state (for container component).
	- saga.js - component saga to manage asynchronous actions (for container component).
