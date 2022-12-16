[be back](https://github.com/ToMikhail/andersen)


# 36. RxJx. Operators (required level 3)

**level 1:**  

- What is Observable;
  -   RxJS представляет собой библиотеку, позволяющую управлять всеми асинхронными операциями и событиями в приложении в стиле реактивного программирования. Мы можем подписаться на stream и отлавливать све что происходит с этим стриомом (все изменения)
  
    - Observable;
    > Объекты RxJS Observable создаются либо с использованием операторов создания (of, from, fromEvent), либо через конструктор new Observable.

    Пример с оператором of().

    ```
    of('Hello').subscribe((vl) => console.log(vl));
      ```
    Пример с new Observable.

    ```
    const obs = new Observable((sub) => {
      sub.next(1);

      setTimeout(() => {
        sub.next(3);
        sub.complete();
      }, 500);
    });

    obs.subscribe((vl) => console.log(vl));
      ```
- What is Subject;
      Subject является разновидностью объектов Observable. Особенность Subject в том, что он может отправлять данные одновременно множеству "потребителей" (multicasetd), которые могут регистрироваться уже в процессе исполнения Subject, в то время как исполнение стандартного Observable осуществляется уникально (uniquecasted) для каждого его вызова.   
      >Объекты RxJS Subject реализуют принцип работы событий, поддерживая возможность регистрировать неограниченное количество обработчиков отправляемых ими данных.   

      ```
      const sbj = new Subject<number>();

      sbj.subscribe((vl) => console.log(`1st: ${vl}`));
      sbj.next(3);
      sbj.subscribe((vl) => console.log(`2nd: ${vl}`));
      sbj.next(9);

      /*
      Результат  в консоли:

      1st: 3
      1st: 9
      2nd: 9
      */
      ```
  
- Promise vs Observable - Promise выполнили один раз и уничтожили данные, Observable - это стрим , кторый можно использовать много раз.;
- Pipe operator;
- Name a few operators that you have used;

**level 2:**  

- Types of Subjects;
    >   В RxJS имеется несколько разновидностей Subject:    
    >  - BehaviorSubject -  хранит в себе последнее отправленное им значение. Так, каждому новому обработчику в момент регистрации (вызов subscribe()) будет отправлено >это значение;   
    >  - ReplaySubject - в отличие от BehaviorSubject объекты ReplaySubject способны хранить заданное количество последних значений, которое задается при создании >объекта;   
    >  - AsyncSubject - в случае с AsyncSubject "потребителям" передается только последнее значение объекта и только, когда он завершит свое выполнение (вызов >complete());   
    >  - AvoidSubject - если не надо выбаваить ничего а сообщить что стрим закончился (пример).
- What do you need to unsubscribe from, and why not;
- What types of unsubscriptions do you know;
  1. Отписаться от стрима через метод unsubscribe()[https://blog.bitsrc.io/6-ways-to-unsubscribe-from-observables-in-angular-ab912819a78f];
  1. Опрераторы take() и first():     
  * take(num) - где num - это количество получаемых входных данных;
  * takeUntil(notifier) => nitifier = new subject() и в методе ngOnDestroy{ notifier.next() и notifier.complete() };
  * takeWhile(val => val < 5);
  * first() - если без аргументов то выдаст первое приходящее значение. если first(val => val === 5) - получим только 5.
  * 
- Difference between takeWhile and takeUntil;
- What are the operators of creation, combination, transformation, error handling;

**level 3:**  

- What is hot, what is cold observable;
  ***Cold Observable (lazy) (unicated)*** - начинают передовать данные только когда мы подпишимся(выполним метод subscribe()) на них. Каждый subscribe() создает отдельный контекст выполнения Observable (пример с получением Math.random - каждый subscribe() вернет разное значение). Создает и активирует данные в Observable;  
  ***Hot observeable (multycasted)*** - получают данные всегда, независмо сделали мы подписку или нет (subscribe()). Создает и активирует данные вне Observable;   
  ***Warm observeable (подогретый)*** - cold observable можно подогреть. Используя оператор multicasted() куда мы передвем Subject(). Затем объединяем два стрима с помощью метожа connect();   
- How to make hot from cold;
- Difference between withLatesFrom, zip, combineLatest, forkJoin, exhaustMap, switchMap, mergeMap;
- Operators multicast, publish, publishReplay, PublishLast, share;

**level 4:** 

- Observable/observer as a software desing pattern

---


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

- marckForCheck vs detectChanges - markForCheck помечает компонент и его дочерние элементы для проверки в следующем цикле вверх по дереву, а detectChanges — фактически сразу запускает механизм обнаружения изменений;
  - cd.detectChanges() немедленно запускает обнаружение изменений от текущего компонента до его потомков.
  - cd.markForCheck() не будет запускать обнаружение изменений, но пометит своих предков как нуждающихся в запуске обнаружения изменений. В следующий раз, когда обнаружение изменений запустится где угодно, оно будет запущено и для тех компонентов, которые были отмечены.
  - https://www.youtube.com/watch?v=OcphK_aEd7I 
- Application.tick vs detectChanges;
  - Application.tick - этот метод для явной обработки обнаружения изменений и его побочных эффектов.
  - **Application.tick** - запускается с root предвставления,** detectChanges()** - запускается с компонента его вызвавшего вниз по дереву

**level 4:** 

- detach(), checkNoChanges(), reattach() - ChangeDetectorRef - Базовый класс, обеспечивающий функциональность обнаружения изменений. Дерево обнаружения изменений собирает все представления, которые необходимо проверить на наличие изменений. Используйте методы, чтобы добавлять и удалять представления из дерева, инициировать обнаружение изменений и явно помечать представления как грязные, что означает, что они изменились и должны быть повторно отображены. абстрактный класс;
  - detach() - Отсоединяет это представление от дерева обнаружения изменений. Отсоединенный вид не проверяется до тех пор, пока он не будет повторно присоединен. Используйте в сочетании с detectChanges() для реализации проверок обнаружения локальных изменений.
  - checkNoChanges() - Проверяет детектор изменений и его дочерние элементы и сбрасывает, если обнаруживаются какие-либо изменения.
  - reattach() - Повторно прикрепляет ранее отсоединенное представление к дереву обнаружения изменений. Представления прикреплены к дереву по умолчанию.
- Architectural advantages of both of strategies;
  - ChangeDetectionStrategy.Default - По умолчанию Angular не делает никаких предположений о том, от чего зависит компонент. Таким образом, он должен быть консервативным и проверять каждый раз, когда что-то могло измениться, это называется грязной проверкой. Более конкретно, он будет выполнять проверки для каждого события браузера, таймеров, XHR и промисов. Это может быть проблематично, когда вы начинаете создавать большое приложение со многими компонентами, особенно если вы сосредоточены на производительности.
  - OnPush - в основном говорите Angular, что он не должен делать никаких предположений о том, когда ему нужно выполнить проверку на наличие изменений. Он будет полагаться только на изменение входных ссылок, некоторые события, инициированные им самим (компонентом) или одним из его дочерних элементов. Наконец, вы, разработчик, можете явно попросить Angular сделать это с помощью метода componentRef.markForCheck().

---


# 38. Angular.Change Detection.ngZone (required level 2)

**level 1:**  

- What is zone.js?
  - zone — это контекст выполнения, который сохраняется для асинхронных задач. Вы можете думать об этом как о локальном хранилище потока для виртуальной машины JavaScript. 
  - https://medium.com/@overthesanity/zone-js-%D0%BE%D1%82-%D0%B0-%D0%B4%D0%BE-%D1%8F-fdb995917968
  - https://www.youtube.com/watch?v=KVeX7oKQxlQ
  - https://www.youtube.com/watch?v=rc3E4tplFCU&t=2964s
  - https://www.youtube.com/watch?v=7LLnPxP8Txw

**level 2:**  

- Zone hooks
  - onScheduleTask - Запускается, когда планируется новая асинхронная задача, например, когда вы вызываете setTimeout().
  - onInvokeTask - Запускается, когда собирается запуститься асинхронная задача, например, когда собирается выполнить обратный вызов setTimeout().
  - onHasTask - Срабатывает, когда статус задачи одного типа внутри зоны изменяется со стабильного на нестабильный или с нестабильного на стабильный. Статус «стабильный» означает, что в зоне нет задач, а «нестабильный» означает, что в зоне запланирована новая задача.
  - onInvoke - Срабатывает, когда в зоне будет выполняться синхронная функция.

**level 3:**  

- run/runOutsideAngular -По умолчанию все асинхронные операции находятся внутри зоны Angular, что автоматически запускает обнаружение изменений.
  - ngZone.run() - позволяет запускать функцию внутри зоны Angular. Эта функция и все асинхронные операции в этой функции автоматически запускают обнаружение изменений в нужное время.
  - runOutsideAngular() - когда вы не хотите инициировать обнаружение изменений. В этой ситуации вы можете использовать другой метод NgZone: runOutsideAngular().

**level 4:** 

- noop Zone; - Чтобы удалить Zone.js, внесите следующие изменения и Bootstrap Angular с зоной noop в src/main.ts
```
platformBrowserDynamic().bootstrapModule(AppModule, { ngZone: 'noop' })
.catch(err => console.error(err));
```

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
