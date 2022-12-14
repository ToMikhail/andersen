[be back](https://github.com/ToMikhail/andersen)


# 36. RxJx. Operators (required level 3)

**level 1:**  

- What is Observable;
- What is Subject;
- Promise vs Observable;
- Pipe operator;
- Name a few operators that you have used;

**level 2:**  

- Types of Subjects;
- What do you need to unsubscribe from, and why not;
- What types of unsubscriptions do you know;
- Difference between takeWhile and takeUntil;
- What are the operators of creation, combination, transformation, error handling;

**level 3:**  

- What is hot, what is cold observable;
- How to make hot from cold;
- Difference between withLatesFrom, zip, combineLatest, forkJoin, exhaustMap, switchMap, mergeMap;
- Operators multicast, publish, publishReplay, PublishLast, share;

**level 4:** 

- Observable/observer as a software desing pattern


# 37. Angular.Change Detection (required level 4)

**level 1:**  

- What is change detection and why is it needed? -это стратегия, с помощью которой Angular решает, какие действия следует выполнять при изменении состояния приложения или компонента.
- Types of change detection strategies;
  - ChangeDetectionStrategy.Default - По умолчанию Angular не делает никаких предположений о том, от чего зависит компонент. Таким образом, он должен быть консервативным и проверять каждый раз, когда что-то могло измениться, это называется грязной проверкой. Более конкретно, он будет выполнять проверки для каждого события браузера, таймеров, XHR и промисов. Это может быть проблематично, когда вы начинаете создавать большое приложение со многими компонентами, особенно если вы сосредоточены на производительности.
  - OnPush - в основном говорите Angular, что он не должен делать никаких предположений о том, когда ему нужно выполнить проверку на наличие изменений. Он будет полагаться только на изменение входных ссылок, некоторые события, инициированные им самим (компонентом) или одним из его дочерних элементов. Наконец, вы, разработчик, можете явно попросить Angular сделать это с помощью метода componentRef.markForCheck().

**level 2:**  

- Difference between strategies OnPush vs Default;
    - Default инициируется проверка при любых изменениях системы (input, event, async, setTimeOut, Observable). Проверятются все компоненты;
    - OnPush - порверяются при    
      1. изменениях ссылок на объект(input), 
      2. events - пользовательские   
      3. Вручную: 
         - DetectChanges() - запускает проверку на этом и н аслед вниз по дереву компонентах
         - componentRef.markForCheck()() - запускается вверхх по дереву при след рендеринге, включая этот элемент;
         - ApplicationRefTick() - инициирует порверку всего приложения (вручную особо не используется)
- What are the triggers for launching change detection for the OnPush strategy;

**level 3:**  

- marckForCheck vs detectChanges;
- Application.tick vs detectChanges;

**level 4:** 

- detach(),checkNoChanges(), reattach();
- Architectural advantages of both of strategies;


# 38. Angular.Change Detection.ngZone (required level 2)

**level 1:**  

- What is zone.js?

**level 2:**  

- Zone hooks

**level 3:**  

- run/runOutsideAngular;

**level 4:** 

- noop Zone;

---

# 39. Angular. Dependency Injection (required level 3)

**level 1:**  

- What is Dependency Injection and why is it needed?
- The main components of Dependency Injection (Dependency, Injector, Provider)
- What can Dependency be?
- What is Injector?
- What is a Provider?

**level 2:**  

- How many injectors are there and how are they located? (In an Angular application, there can be several of these injectors, they are located in a tree hierarchy parallel to the component tree)
- What are the ways to provide a dependency to the injector (providers, viewProviders, @Injectable)?
- What defines a provider?

**level 3:**  

- @Inject () and @Injectable () what is the difference?
- What is useClass, useValue, useFactory, useExisting;
- How does Angular look for a supplier in the injector hierarchy?
- What are viewProviders?

**level 4:** 

- Why do we need @Optional, @Host, @Self, @SkipSelf decorators
- flag multi: true why is it?
- What are tree-shakable providers?
- Handmade injector;

---


# 40. Angular. Testing. Unit (required level 3)

**level 1:**  

**level 2:**  

- Test bed. Why do we need it?

**level 3:**  

- Testing components/services

**level 4:** 

- Testing directives;
- Testing pipes;

---

# 41. Angular. Extra. CLI (required level 2)

**level 1:**  

**level 2:**  

**level 3:**  

- generate, add, build, serve etc

**level 4:**   

- angular.json. What is it about

---

# 42. Angular. Extra. Ivy (required level 2)

**level 1:**  

**level 2:**  

**level 3:**  

**level 4:** 

- What is Ivy?

---

# xx. Nam (required level x)

**level 1:**  

**level 2:**  

**level 3:**  

**level 4:** 
