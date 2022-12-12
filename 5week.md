[be back](https://github.com/ToMikhail/andersen)


# 31. Unit-tests, testing pyramid, integration tests (required level 3)

**level 1:**  

Проверка соответствия между реальным и ожидаемым поведением программы, осуществляемая на конечном наборе тестов, выбранном определенным образом.

- Basic concepts: 
  - Test Plan - Используются для группирования наборов тестов и отдельных тестовых случаев.
  - Test Suite - Группируйте тестовые случаи в отдельные сценарии тестирования в рамках одного тестового плана. Группирование тестовых случаев упрощает просмотр сценариев завершения. При создании набора тестов можно указать один из трех типов:
    - Статические наборы тестов: используется для группирования тестовых случаев в одном наборе тестов.
    - Наборы на основе требований: выберите один или несколько требований из запроса, который затем связан с набором тестов.
    - Наборы на основе запросов: выберите один или несколько тестовых случаев, которые затем связаны с набором тестов.
  - Test Case – это тестовый артефакт, суть которого заключается в выполнении некоторого количества действий и/или условий, необходимых для проверки определенной функциональности разрабатываемой программной системы.
 
**level 2:**  

- Testing Pyramid - Пирамида тестирования, также часто говорят уровни тестирования, это группировка тестов по уровню детализации и их назначению. Эту абстракцию придумал Майк Кон и описал в книге «Scrum: гибкая разработка ПО» (Succeeding With Agile. Software Development Using Scrum).
  Пирамиду разбивают на 4 уровня (снизу вверх), например:     
  •	модульное тестирование (юнит);
  •	интеграционное тестирование;
  •	системное тестирования;
  •	приемочное тестирование.

**level 3:**  

- Different test types concepts: Unit/Integration/Functional
   - Существует несколько признаков, по которым принято производить классификацию видов тестирования. Обычно выделяют следующие:
      По объекту тестирования:
      •	Функциональное тестирование
      •	Тестирование производительности
      •	Конфигурационное тестирование
      •	Юзабилити-тестирование
      •	Тестирование безопасности
      •	Тестирование локализации
      •	Тестирование совместимости

      По степени автоматизации:
      •	Ручное тестирование
      •	Автоматизированное тестирование
      •	Полуавтоматизированное тестирование

      По степени изолированности:
      •	Тестирование компонентов
      •	Интеграционное тестирование
      •	Системное тестирование

      По степени подготовленности к тестированию:
      •	Тестирование по документации (формальное тестирование)
      •	Интуитивное тестирование

      По знанию внутреннего строения системы:
      •	Тестирование чёрного ящика
      •	Тестирование белого ящика
      •	Тестирование серого ящика

- Properties of a good unit test; - https://habr.com/ru/post/555402/
  - Интегрированы в цикл разработки. Пользу приносят только те тесты, которые вы активно используете; иначе писать их нет смысла.
  - Тестируют только самые важные части вашего кода. Не весь рабочий код заслуживает одинакового внимания.
  - Дают максимальную защиту от багов с минимальными затратами на сопровождение. Для этого нужно уметь распознавать эффективные тесты и писать их.
- F.I.R.S.T;
  - Fast - тесты должны быть невероятно быстрыми, чтобы их хотелось запускать как можно чаще
  - Independent - тесты не должны зависеть от результатов выполнения других тестов
  - Repeatable - тесты должны всегда выдавать одинаковый результат в любом окружении
  - Self-Validating - результат выполнения тестов бинарен и полностью автоматизирован. Разработчик должен видеть явный ответ тесты прошли или нет.
  - Timely - тест должен быть написан вовремя, то есть прямо перед кодом который позволит тесту пройти успешно.
- JS Unit basics;

**level 4:** 

- Test first development techniques (TDD and BDD) - TDD проверяет работу функций, BDD — пользовательские сценарии.
  - TDD (Test Driven Development) — Разработка на основе тестов.
  - BDD (Behavior Driven Development) — Разработка на основе поведения.

# 32. Regular Expressions, RegExp (required level 2)

**level 1:**  

- What is RegExp - мощное средство поиска и замены в строке. - https://learn.javascript.ru/regexp-introduction
- How to use RegExp

**level 2:**  

- Two methods of RegExp object - в JavaScript объект RegExp представляет собой объект регулярного выражения с предопределенными свойствами и методами;
  - str.match(regexp) - Метод str.match(regexp) для строки str возвращает совпадения с регулярным выражением regexp.
  ```
  let str = "Любо, братцы, любо!";
  alert( str.match(/любо/gi) ); // Любо,любо (массив из 2х подстрок-совпадений)
  ```
  
  - str.replace(regexp, replacement) - заменяет совпадения с regexp в строке str на replacement (все, если есть флаг g, иначе только первое).
  ```
  // без флага g
  alert( "We will, we will".replace(/we/i, "I") ); // I will, we will

  // с флагом g
  alert( "We will, we will".replace(/we/ig, "I") ); // I will, I will
  ```
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

- Two ways to create RegExp; - Символьный класс – это специальное обозначение, которое соответствует любому символу из определённого набора. - https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/RegExp
  - Литеральное обозначение принимает шаблон между двумя косыми чертами, за которыми следуют необязательные флаги после второй косой черты. 
  - Функция-конструктор принимает строку или объект RegExp в качестве первого параметра и строку необязательных флагов в качестве второго параметра.

**level 4:**  

- Basic RegExp pattern (character classes);
  - character classes - https://learn.javascript.ru/regexp-character-classes
  - https://learn.javascript.ru/regular-expressions

# 33. Angular. Pipes (required level 4)

**level 1:**  

- What is a pipe; - это класс для изменения внешнего вида данных в шаблоне. В декортаторе есть поле name @Pipe({name: 'pipeName'});
  >Какие бывают встроенные pipes (доступны благодоря BroserModule in app.module.ts):   
  >* {var | number | uppercase | lowercase | titlecase | slice:a:5 | percent | cerncy | date:'long' | async}  
  
- What are they needed for; - В декортаторе есть поле name @Pipe({name: 'pipeName'})

**level 2:**  

- How do implement a custom pipe; - Необходимо  класс implements от interface PipeTransform и реализовать метод в нем transform(мvalue, args) + decorator @Pipe({ name: 'pipeName'}). 
- How do pass a parameter to a pipe; - Example ({{ vavr | number: '1.1-5'}})

**level 3:**  

- What parameters does transform() take - Необходимо implements класс от PipeTransform и метод в нем transform. (value - что обрабатываем и args(либо arg) - можно и без него)

**level 4:** 

- Custom async pipes;
  >Что бы сделать из Pure Impure Pipe неоьбходимо добавиьт поле **pure: false**  в декортаторе
- pure vs. impure pipes;
  Pipes  могут быть: 
  - Pure(чистые) - отрабатывают на изменения ссылки;
  - Impure(нечистые) - этрабатывает на все изменения, не только ссылки это async, json;
  
- Async pipe;
  для работы со стримами с promise, observable, setTimout, что бы вывести инфу надо использовать async Pipe, иначе вывод [Object Promise]


# 34. Reactive Forms (required level 4)

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


# 35. RxJx. Operators (required level 3)

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


# 36. Angular.Routing (required level 3)

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


# 37. Angular.Change Detection (required level 4)

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


# 38. Angular.Change Detection.ngZone (required level 2)

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
