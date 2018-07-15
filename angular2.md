# Angular 2

Modules : added in ES 2015
* to export a class, use
	export class Product { ... } in product.ts
* to import a class, use
	import { Product } from './product'


Don't add extension to product in importing process, as it gets transpile from ts to js


## 1. Component
* Includes
	+ templates
	+ class : ts method, properties
	+ metadata : decorator
#### creating component class
ex :
----
in app.component.ts

export class AppComponent {
			PageTitle: string = 'A. P. Ma.';
			}
			Property name, Data type, Default value

----
* class become component when component is added
* @Component decorator before class
	- import it from 'angular/core'
	- is a function with a object
	- must have template
	- data binding with {{...}}
	- selector : ??? : used to identify in HTML

SPA - Single Page application
* index.html contains the main page of the application

bootstrapper : main.ts
* use it in index.html as System.import('app/main')

# Template, Interpolation, Directives
