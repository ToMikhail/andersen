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
   - Шаблонный подход (template driven forms);
   - Реактивный подход (Reactive forms). Через controls - это экземпляры класса FornControl, FormGroup, FormArray, FormBuilder;

    Различия между template-driven forms и Reactive forms:  
      - *Reactive forms* - sync, *template-driven forms* - async; 
      - *Reactive forms* - управление происходит в класса модели (component). Богатая API. *template-driven form* - управление происходит в шаблоне (в html)          (фактически 2-way binding ( [(ngModel)]='var'));
      - *Reactive forms*- для сложных форм. *template-driven form* - для протсоых форм;
      - *Reactive forms* - гибкость настроек;
      - 
- What is FormControl, FormGroup; - это экземпляры класса FornControl, FormGroup, FormArray, FormBuilder;
- How do we link form elements in a template and a component;

**level 2:**  

- What is FormBuilder -  предоставляет синтаксический сахар, который сокращает создание экземпляров FormControl, FormGroup или FormArray. Это уменьшает количество шаблонов, необходимых для создания сложных форм., 
- FormArray; - объединяет значения каждого дочернего элемента FormControl в массив
- What's the difference between a dirty, touched, and pristine form element;
  заимодействие с валидаторами состояния INPUT (Статусы состояния(Кдассы в html в браузере)). Валидаторы имеют следующие состояния:
    pristine - когда еще ничего не вводили;
    dirty - когда что то ввели;
    touched - когда было переведено в focus;
    untouched - когда не было переведено в focus, не тронуто;
    valid - когда пройдена валидация;
    invalid - когда не пройдена валидация;
    pending - когда ждем ответа от валидатора
    
 - How does the form validation work;
> Валидатор (validator) - это функция которая возращает функцию (ValidatorFn) которая получает control и синхронно возвращает карту ошибок проверки, если они есть, в >противном случае — null.

  >Валидаторы (validator) для форм бывают:
  > - встроенные (built-in) - required, email, pattern и minLength;
  > - пользовательский (custom validators);
  >и
  > - async;
  > - sync;

**level 3:**  

- How to add / remove validator after form initialization? (setValidators, clearValidators)
  - setValidators() - Задает синхронные валидаторы, активные для этого элемента управления. Вызов этого перезаписывает любые существующие синхронные валидаторы.
  ```
  this.myform.controls["mobile"].setValidators(Validators.required);
  ```
  clearValidators - Не существует опции, которая может удалить отдельный валидатор. Используйте clearValidators, чтобы удалить все валидаторы элемента управления.
  ```
  this.myForm.controls['controlName'].clearValidators()
  ```

**level 4:**

- Dealing with errors of the form setErrors, getError, hasError
  - setErrors - Устанавливает ошибки в элементе управления формы при выполнении проверок вручную, а не автоматически
  ```
  this.form.get('name').setErrors({'server-error':'error'});
  ```
  - getError() - Сообщает данные об ошибках для control с заданным путем
  - hasErroro() - Сообщает, имеет ли элемент управления с заданным путем указанную ошибку.
  

# 35. Angular.Routing (required level 3)

**level 1:**  

- Initialising router;
    1.Создаем компоненты страницы приложения (страницы или routes);     
    2. создаем routing модуль, который содержит @NgModule декоратор со свойствами imports и exports. И в imports передаем пути для строниц (routes). routes - это массив объектов [{},{},{}] со свойствами path: 'путь до строницы', component: имя класса отвечающего за компонент, (это обязательные), и по требованию свойство children: с массивом обхектов (дочерних страниц). Вместо component может идти свойство redirectTo c указанием страницы (route) куда необходимо перенаправить в случае неверног гзадание ссылки (ошибка в пути).    
    3. Регестрируем созданный модуль с app.module.ts в imports [];    
    4. В app.component.html => прописывается тег router-outlet
  ```
  const routes: Routes = [
  {path: '', component: HomeComponent},
  {path: 'about', component: AboutComponent, children: [
    {path: 'extra', component: AboutExtraComponent}
  ]},
  {path: 'posts', component: PostsComponent},
  {path: 'posts/:id', component: PostComponent},
  {path: '**', redirectTo: ''},
  ]

    @NgModule({
      imports: [RouterModule.forRoot(routes)],
      exports: [RouterModule],
    })
    export default class AppRoutingModule {}
  ```
  - Explain behind such properties in a route config object:    
        -path - Путь для сопоставления     
        -pathMatch - используется совместно с redirectTo     
        -component - компонент для отображения при переходе на URL, совпадающий с path;      
        -redirectTo - перенаправляет на указанный URL при попадании на маршрут, указанный в path     
        -data - Дополнительные определенные разработчиком данные, предоставляемые компоненту через ActivatedRoute. По умолчанию никакие дополнительные данные не передаются.;
        
- Rroute event;
  - NavigationStart - начало навигации;
  - RoutesRecognized - завершение процесса парсинга URL и распознавания маршрутов;
  - RouteConfigLoadStart - инициируется непосредственно перед асинхронной загрузкой маршрутов;
  - RouteConfigLoadEnd - инициируется непосредственно после асинхронной загрузкой маршрутов;
  - NavigationEnd - завершение навигации;
  - NavigationCancel - навигация отклонена, возникает, когда guard возвращает false;
  - NavigationError - возникновение непредвиденной ошибки в процессе осуществления навигации.

**level 2:**  

- What is Router Guard - позволяют ограничить доступ к маршрутам на основе определенного условия, например, только авторизованные пользователи с определенным набором прав могут просматривать страницу.;
- Router Events order;
- Define Route
  - Получить значение параметра и свойства data позволяет сервис ActivatedRoute. В его экземпляре, определенном для компонента-маршрута, содержится полная информация.
- ActivatedRoute
- ParamMap - В шаблоне параметры маршрутизации передаются следующим образом: в качестве значения директивы указывается массив, первое значение которого URL, второе — значение параметра данного URL.;
- ActivatedRoute vs ActivatedRouteSnapshot -  ActivatedRoute можно использовать повторно, ActivatedRouteSnapshot — это неизменяемый объект, представляющий конкретную версию ActivatedRoute.;

**level 3:**  

- What's the difference between canLoad and canActivate;  
  - CanMatch - разрешает видеть или не видеть маршрут (route) - 1-й проверяется в "жизненном цикле";
  - CanLoad - разрешает/запрещает загрузку модуля, загружаемого асинхронно - 2-й проверятеся;.
  - CanDeactivate - разрешает/запрещает уход с текущего маршрута - 3-й проверятеся;
  - CanActivate - разрешает/запрещает доступ к маршруту - 4-й проверятеся;;
  - CanActivateChild -разрешает/запрещает доступ к дочернему маршруту - 5-й проверятеся;;
  - Resolve - выполняет какое-либо действие перед переходом на маршрут, обычно ожидает данные от сервера - 6-й проверятеся;;
  
- What are child routes;
- What are Resolvers; - для аутенфикации; - используется в сценарии, когда мы хотим убедиться, что данные доступны или нет, прежде чем перейти к какому-либо маршруту.
- What is Lazy loading; = Вы можете настроить свои маршруты для отложенной загрузки модулей, что означает, что Angular загружает модули только по мере необходимости, а не загружает все модули при запуске приложения. Кроме того, предварительно загрузите части вашего приложения в фоновом режиме, чтобы улучшить взаимодействие с пользователем. 

**level 4:** 

- paramMap vs queryParamMap; 
  - ParamMap для таких маршрутов, как user/:id. Id param принадлежит только этому маршруту.
  - queryParamMap - это глобальный параметр запроса, его можно прочитать из ActivatedRoute в компоненте пользовательского маршрута, а также из любого из его предков.
приложения.
  - PreloadingStrategy - определяет логику предварительной загрузки и обработки лениво загруженных модулей Angular. Чтобы лениво загружать модули Angular, используйте loadChildren (вместо компонента) в конфигурации маршрутов AppRoutingModule следующим образом.
  - Eager loading (default)- это стратегия загрузки по умолчанию для компонентов в Angular. Он впервые загружает все компоненты, зарегистрированные в NgModules 
  - PreloadAllModules, which preloads all lazy-loaded routes, as the name implies
  - QuicklinkStrategy, which preloads only the routes associated with links on the current page.
- Events tracing/debugging - Включает регистрацию всех внутренних событий навигации на консоли. Дополнительное ведение журнала может быть полезно в целях отладки для проверки последовательности событий маршрутизатора.;
  ```
  const appRoutes: Routes = [];
  bootstrapApplication(AppComponent,
    {
      providers: [
        provideRouter(appRoutes, withDebugTracing())
      ]
    }
  );
  ```

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
