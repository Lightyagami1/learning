# Angular 2

Modules : added in ES 2015
* to export a class, use
	export class Product { ... } in product.ts
* to import a class, use
	import { Product } from './product'


Don't add extension to product in importing process, as it gets transpile from ts to js

# IMP : maintain relative path from index.html

## 1. Component
* Includes
	+ templates
	+ class : ts method, properties
	+ metadata : decorator
#### creating component class
in app.component.ts

```javascript
export class AppComponent {
			PageTitle: string = 'A. P. Ma.';
			}
			Property name, Data type, Default value
```
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

# 2. Template, Interpolation, Directives

## BINDING 
* coordinates communication between the component class and it's template
* INTERPOLATION
 * {{ ... }} 
 * use whenever some value is to be displayed

* DIRECTIVE
 - for logic to extend HTML
 - can be
  + custom
  + build in
   - *ngIf
   - *ngFor
# 3. Data Bindings & Pipes
## Property Binding
* Ex : <img [src] = 'product.imageUrl'>

## event binding

DOM : Document Object Model

## Two way binding
 * Banana in a box : [(ngModel)] = ...
 * uses ngModel

## Transform data by Pipes
* add | lowercase : this convert string to lower case
* can be chained like {{prod.price | currency | lowercase }}

# 7. More on Components
## Interface
* a specification indentifying a related set of properties and methods
* prevent error and resulting in maintainable code

## CSS
* add styleUrls or inline style as array
* styleUrls: ['relative address from index.html'] -> it's a array still

## custom pipes
