[be back](https://github.com/ToMikhail/andersen)


# 31. Regular Expressions, RegExp (required level 2)

**level 1:**  

- What is RegExp - https://learn.javascript.ru/regexp-introduction
- How to use RegExp

**level 2:**  

- Two methods of RegExp object - в JavaScript объект RegExp представляет собой объект регулярного выражения с предопределенными свойствами и методами;
  - test() - Он ищет в строке шаблон и возвращает true или false в зависимости от результата.
    - https://learn.javascript.ru/regexp-introduction#proverka-regexp-test
    - https://learn.javascript.ru/regexp-methods#regexp-test-str
  ```
  const pattern = /e/;
  pattern.test("The best things in life are free!");
  ```
  - exec() - Он ищет в строке указанный шаблон и возвращает найденный текст в виде объекта. - Он ищет в строке указанный шаблон и возвращает найденный текст в виде объекта. Если совпадений не найдено, возвращается пустой (нулевой) объект. В следующем примере выполняется поиск в строке символа «e»
    -  https://learn.javascript.ru/regexp-methods#regexp-exec-str
  ```
  /e/.exec("The best things in life are free!");
  ```

**level 3:**  

- Two ways to create RegExp; - https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/RegExp
  - Литеральное обозначение принимает шаблон между двумя косыми чертами, за которыми следуют необязательные флаги после второй косой черты. 
  - Функция-конструктор принимает строку или объект RegExp в качестве первого параметра и строку необязательных флагов в качестве второго параметра.

**level 4:**  

- Basic RegExp pattern (character classes);
  - character classes - https://learn.javascript.ru/regexp-character-classes
  - https://learn.javascript.ru/regular-expressions

# 32. Angular. Pipes (required level 4)

**level 1:**  

- What is a pipe;
- What are they needed for;

**level 2:**  

- How do implement a custom pipe;
- How do pass a parameter to a pipe;

**level 3:**  

- What parameters does transform() take

**level 4:** 

- Custom async pipes;
- pure vs. impure pipes;
- Async pipe;


# 33. Reactive Forms (required level 4)

**level 1:**  

- What's the difference between Template Driven Form and Reactive Form;
- What is FormControl, FormGroup;
- How do we link form elements in a template and a component;

**level 2:**  

- What is FormBuilder, FormArray;
- What's the difference between a dirty, touched, and pristine form element;
- How does the form validation work;

**level 3:**  

- How to add / remove validator after form initialization? (setValidators, clearValidators)

**level 4:**

- Dealing with errors of the form setErrors, getError, hasError


# 34. RxJx. Operators (required level 3)

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


# 35. Angular.Routing (required level 3)

**level 1:**  

- Initialising router;
- Explain behind such properties in a route config object:
        -path
        -pathMatch
        -component
        -redirectTo
        -data;
- Rroute event;

**level 2:**  

- What is Router Guard;
- Router Events order;
- Define Route / ActivatedRoute / ParamMap;
- ActivatedRoute vs ActivatedRouteSnapshot;

**level 3:**  

- What's the difference between canLoad and canActivate;
- What are child routes;
- What are Resolvers;
- What is Lazy loading;

**level 4:** 

- paramMap vs queryParamMap;
- PreloadingStrategy;
- Events tracing/debugging;


# 36. Angular.Change Detection (required level 4)

**level 1:**  

- What is change detection and why is it needed?
- Types of change detection strategies;

**level 2:**  

- Difference between strategies OnPush vs Default;
- What are the triggers for launching change detection for the OnPush strategy;

**level 3:**  

- marckForCheck vs detectChanges;
- Application.tick vs detectChanges;

**level 4:** 

- detach(),checkNoChanges(), reattach();
- Architectural advantages of both of strategies;


# 37. Angular.Change Detection.ngZone (required level 2)

**level 1:**  

- What is zone.js?

**level 2:**  

- Zone hooks

**level 3:**  

- run/runOutsideAngular;

**level 4:** 

- noop Zone;




# xx. Nam (required level x)

**level 1:**  

**level 2:**  

**level 3:**  

**level 4:** 
