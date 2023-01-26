

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

Types of injector hierarchies:
 - ModuleInjector hierarchy - Configure a ModuleInjector in this hierarchy using an @NgModule() or @Injectable() annotation.
 - ElementInjector hierarchy - Created implicitly at each DOM element. An ElementInjector is empty by default unless you configure it in the providers property on @Directive() or @Component().
There are two more injectors above root, an additional ModuleInjector and NullInjector().

### Provider   
A provider is an instruction to the Dependency Injection system on how to obtain a value for a dependency. Most of the time, these dependencies are services that you create and provide.

The provider-definition key can be one of the following:
 - useClass - this option tells Angular DI to instantiate a provided class when a dependency is injected;
 - useExisting - allows you to alias a token and reference any existing one.
 - useFactory - allows you to define a function that constructs a dependency.
 - useValue - provides a static value that should be used as a dependency.

If you specify the service class as the provider token, the default behavior is for the injector to instantiate that class using the new operator.

### resolution modifiers:
 - @Optional() - allows Angular to consider a service you inject to be optional. This way, if it can't be resolved at runtime, Angular resolves the service as null, rather than throwing an error.
 - @SkipSelf() - With @SkipSelf(), Angular starts its search for a service in the parent ElementInjector, rather than in the current one.
 - @Host() - @Host() lets you designate a component as the last stop in the injector tree when searching for providers. Even if there is a service instance further up the tree, Angular won't continue looking Use @Host() as follows;
 - @Self() - Use @Self() so that Angular will only look at the ElementInjector for the current component or directive


## Change detection
Change detection is the process through which Angular checks to see whether your application state has changed, and if any DOM needs to be updated.  
 At a high level, Angular walks your components from top to bottom, looking for changes. Angular runs its change detection mechanism periodically so that changes to the data model are reflected in an application’s view.   
Change detection can be triggered either manually or through an asynchronous event (for example, a user interaction or an XMLHttpRequest completion).  

Change detection is a highly optimized performant, but it can still cause slowdowns if the application runs it too frequently;

2 types of Change Detection Strotegy: 
 - Default - run Change detection through any changes;
 - onPush - run Change detection only when was changed value( immutable changes) or happen user events or mannually (detectChanges(), markFo Check, Application.tick()); 
Use OnPush strategy if your objects are immutable and you don't change the state of the objects in your component. It will perform better rather than default where each change of the object makes run change detector to resolve changes


### Zone.js
Zone.js is a signaling mechanism that Angular uses to detect when an application state might have changed. It captures asynchronous operations like setTimeout, network requests, and event listeners. 
Angular schedules change detection based on signals from Zone.js   
In such cases, you can instruct Angular to avoid calling change detection for tasks scheduled by a given piece of code using NgZone


##Life cycle hooks
A component instance has a lifecycle that starts when Angular instantiates the component class and renders the component view along with its child views. The lifecycle continues with change detection, as Angular checks to see when data-bound properties change, and updates both the view and the component instance as needed. The lifecycle ends when Angular destroys the component instance and removes its rendered template from the DOM. Directives have a similar lifecycle, as Angular creates, updates, and destroys instances in the course of execution.
 - ngOnChanges - When an input or output binding value changes.
 - ngOnInit - After the first ngOnChanges.
 - ngDoCheck - Developer's custom change detection.
 - ngAfterContentInit - After component content initialized.
 - ngAfterContentChecked - After every check of component content.
 - ngAfterViewInit - After the views of a component are initialized.
 - ngAfterViewChecked - After every check of the views of a component.
 - ngOnDestroy - Just before the directive is destroyed.


## Reactive forms
 - template-driven forms - A format for building Angular forms using HTML forms and input elements in the view.
 - reactive forms - A framework for building Angular forms through code in a component. 
  When using reactive forms: 
   - The "source of truth", the form model, is defined in the component class.
   - Validation is set up through validation functions rather than validation directives.
   - Each control is explicitly created in the component class by creating a FormControl instance manually or with FormBuilder.
   - The template input elements do not use ngModel.
   - The associated Angular directives are prefixed with form, such as formControl, formGroup, and formControlName.


## Routing
 1. Import RouterModule and Routes into your routing module
 ```
 import { NgModule } from '@angular/core';
 import { Routes, RouterModule } from '@angular/router'; // CLI imports router

 const routes: Routes = []; // sets up routes constant where you define your routes

 // configures NgModule imports and exports
 @NgModule({
  imports: [RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
 ```
 2. Define your routes in your Routes array
```
 const routes: Routes = [
  { path: 'first-component', component: FirstComponent },
  { path: 'second-component', component: SecondComponent },
 ];
```
 3. Add your routes to your application (routerLink and <router-outlet></router-outlet>)

## Preloading Strategy 
Angular Preloading Strategy is yet another way to speed up the load time of the Angular Apps. We build Modular apps using the Angular Modules. The Angular loads all the modules, when the user requests for the first time. This will make app loading slowly as it need to download all the modules


lazy loading - just need to add LoadChildren for root routing module

The Angular provides two built in strategies out of the box. one is PreloadAllModules and other one is NoPreloading:
 - PreloadAllModules - This strategy will preload all the lazy loaded modules. 
 - NoPreloading - This will disables all the preloading. This is default behavior i.e. if you don not specify the preloadingStrategy, then the angular assumes you do not want preloading

##Guards
The Angular router’s navigation guards allow to grant or remove access to certain parts of the navigation. Another route guard, the CanDeactivate guard, even allows you to prevent a user from accidentally leaving a component with unsaved changes.  
  
Here are the 4 types of routing guards available:
  - CanActivate: Controls if a route can be activated.
  - CanActivateChild: Controls if children of a route can be activated.
  - CanLoad: Controls if a route can even be loaded. This becomes useful for feature modules that are lazy-loaded. They won’t even load if the guard returns false.
  - CanDeactivate: Controls if the user can leave a route. Note that this guard doesn’t prevent the user from closing the browser tab or navigating to a different address. It only prevents actions from within the application itself.

## Interceptor 
The angular interceptor is a medium connecting the backend and front-end applications. Whenever a request is made, the interceptors handle it in between. They can also identify the response by performing Rxjs operators. The interceptors do not initiate the handle method and handle the requests at their level

## RXJS

### Observable
Observables are lazy Push collections of multiple values. They fill the missing spot in the following table:   
A producer of multiple values, which it pushes to subscribers. Used for asynchronous event handling throughout Angular. You execute an observable by subscribing to it with its subscribe() method, passing callbacks for notifications of new values, errors, or completion.  

### Observer
An object passed to the subscribe() method for an observable. The object defines the callbacks for the subscriber. (next, error, complete)

### Hot and Cold Observable (multicasted, lazy)
Hot Observable - Hot observables are ones that are pushing event when you are not subscribed to the observable.
Cold Observable starts producing data when some code invokes a subscribe() function on it.   

The main difference is that a cold observable creates a data producer for each subscriber, whereas a hot observable creates a data producer first, and each subscriber gets the data from one producer, starting from the moment of subscription.

For creatinf Warm Obsevable we should use multicast operator.

###Subject
What is a Subject? An RxJS Subject is a special type of Observable that allows values to be multicasted to many Observers.

  - BehaviorSubject - One of the variants of Subjects is the BehaviorSubject, which has a notion of "the current value". It stores the latest value emitted to its consumers, and whenever a new Observer subscribes, it will immediately receive the "current value" from the BehaviorSubject.
  - ReplaySubject - A ReplaySubject records multiple values from the Observable execution and replays them to new subscribers. When creating a ReplaySubject, you can specify how many values to replay;
  - AsyncSubject - The AsyncSubject is a variant where only the last value of the Observable execution is sent to its observers, and only when the execution completes.

### Higher-order Observables
Observables most commonly emit ordinary values like strings and numbers, but surprisingly often, it is necessary to handle Observables of Observables, so-called higher-order Observables.   
But how do you work with a higher-order Observable? Typically, by flattening: by converting a higher-order Observable into an ordinary Observable.   
 - mergeMap() - subscribes to each inner Observable as it arrives, then emits each value as it arrives;
 - exhaustMap() — subscribes to the first inner Observable when it arrives, and emits each value as it arrives, discarding all newly arriving inner Observables until that first one completes, then waits for the next inner Observable.
 - switchMap() — subscribes to the first inner Observable when it arrives, and emits each value as it arrives, but when the next inner Observable arrives, unsubscribes to the previous one, and subscribes to the new one.
 - concatMap() operator subscribes to each "inner" Observable, buffers all further emissions of the "outer" Observable, and copies all the emitted values until the inner Observable completes, and continues processing the values of the "outer Observable"


