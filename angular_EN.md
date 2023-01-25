

#  Angular 

Angular is an application-design framework and development platform for creating efficient and sophisticated single-page apps.
 
 ## Component
 Components are the building blocks that compose an application. A component includes a TypeScript class with a @Component() decorator, an HTML template, and styles. 
 The @Component() decorator specifies the following Angular-specific information:
  - A CSS selector that defines how the component is used in a template. HTML elements in your template that match this selector become instances of the component.
  - An HTML template that instructs Angular how to render the component
  - An optional set of CSS styles that define the appearance of the template's HTML elements

## Directives
Directives are classes that add additional behavior to elements in your Angular applications. Use Angular's built-in directives to manage forms, lists, styles, and what users see.
The different types of Angular directives are as follows:
  - Components - Used with a template. This type of directive is the most common directive type;
  - Attribute directives - Change the appearance or behavior of an element, component, or another directive. (NgClass, NgStyle, NgModel)
  - Structural directives - Change the DOM layout by adding and removing DOM elements.(NgIf, NgFor, NgSwitch)

## Pipe
Use pipes to transform strings, currency amounts, dates, and other data for display.   
Pipes are simple functions to use in template expressions to accept an input value and return a transformed value. 
Pipes are useful because you can use them throughout your application, while only declaring each pipe once. (data , number, currency, percent, uppercase, lowercase)

  - pure - is only called when Angular detects a change in the value or the parameters passed to a pipe
  - impure -  is called for every change detection cycle no matter whether the value or parameter(s) changes. 
  This is relevant for changes that are not detected by Angula


## Dependency injection
Dependency injection lets you declare the dependencies of your TypeScript classes without taking care of their instantiation. Instead, Angular handles the instantiation for you. This design pattern lets you write more testable and flexible code.   
Dependency Injection, or DI, is a design pattern and mechanism for creating and delivering some parts of an application to other parts of an application that require them. 
Angular supports this design pattern and you can use it in your applications to increase flexibility and modularity.
>Dependency injection, or DI, is one of the fundamental concepts in Angular. DI is wired into the Angular framework and allows classes with Angular decorators, such as Components, Directives, Pipes, and Injectables, 
>to configure dependencies that they need.

##Change detection
Change detection is the process through which Angular checks to see whether your application state has changed, and if any DOM needs to be updated.  
 At a high level, Angular walks your components from top to bottom, looking for changes. Angular runs its change detection mechanism periodically so that changes to the data model are reflected in an application’s view.   
Change detection can be triggered either manually or through an asynchronous event (for example, a user interaction or an XMLHttpRequest completion).  

Change detection is a highly optimized performant, but it can still cause slowdowns if the application runs it too frequently

### Zone.js
Zone.js is a signaling mechanism that Angular uses to detect when an application state might have changed. It captures asynchronous operations like setTimeout, network requests, and event listeners. 
Angular schedules change detection based on signals from Zone.js   
In such cases, you can instruct Angular to avoid calling change detection for tasks scheduled by a given piece of code using NgZone


##Life cycle hooks





