[be back](https://github.com/ToMikhail/andersen)

# 24. Programming paradigms (imperative and declarative)"

**level 1:** 

- Anderstanding what is paradigm - Паради́гма программи́рования — это совокупность идей и понятий, определяющих стиль написания компьютерных программ (подход к программированию). Это способ концептуализации, определяющий организацию вычислений и структурирование работы, выполняемой компьютером.

**level 2:**  

- What is Imperative and Declarative 
  - Императивное программирование — это парадигма, основанная на составлении алгоритма действий (инструкций/команд), которые изменяют состояние (информацию/данные/память) программы. (цмкл for while). Программирование, при котором вы пишите инструкцию компьютеру, как он должен работать, называется императивным программированием.
Читая код, вы можете понять, что он делает, но возникает недоумение: зачем нужны эти шаги, к чему они приведут?
Такой код длиннее и его сложнее понять с первого взгляда.
  - Декларотивный программированиеЭтот подход, который заключается в указании какого результата вы хотите достичь, вместо шагов, необходимых для его получения. Это называется декларативным программированием. В это случае, появляется больше смысла. Вы берете все числа, отфильтровываете нечетные, затем удваиваете остальные и складываете их. Кроме того, он более лаконичен, и шаги, необходимые для получения результата, более понятны.
  - https://habr.com/ru/post/324688/
  - https://medium.com/@wladislawross/%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-%D0%B4%D0%B5%D0%BA%D0%BB%D0%B0%D1%80%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B9-%D0%B8%D0%BC%D0%BF%D0%B5%D1%80%D0%B0%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B9-%D0%BF%D0%BE%D0%B4%D1%85%D0%BE%D0%B4-d348b7383607

**level 3:**  

- Imperative vs Declarative main diferences

**level 4:** 

- Imperative and Declarative - examples of eac paradigm

# 25. Functional programming (functors, Key Features) (required level x)

**level 1:**  

- https://habr.com/ru/company/touchinstinct/blog/314510/

**level 2:**  

- What is FP - это парадигиа програмировагия, предпологающая обходится вычислениями результатов ф-ций от исходных данных и результатов других ф-ций и не предпологает явного хранения состояния программы;

**level 3:**  

- What is  main feature of FP - 
  - Чистые функции (рекурсия) - Функция всегда возвращает один и тот же результат при одних и тех же входных параметрах. И вычисление результата не вызывает видимых семантических побочных эффектов
  - Иммутабельность данных
  - Композиция - вызов функции в качестве аргументов др ф-ций
  - Функции высшего порядка - Это функция, которая оперирует другими функциями. Оперирует, получая их в качестве параметра или возвращая их.
  - Каррирование - преобразование ф-ций с множеством аргументов в набор вложенных фуекций с аргументами. Каррирование – это трансформация функций таким образом, чтобы они принимали аргументы не как f(a, b, c), а как f(a)(b)(c). 
    - https://learn.javascript.ru/currying-partials
  - Частичное применение - преобразование функции в другую функцию обладающую меньшим числом аргументов;
  
  - https://doka.guide/js/fp/#:~:text=%D0%A4%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D0%B5%20%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D0%BF%D0%BE%20%D1%81%D1%83%D1%82%D0%B8%20%E2%80%94%20%D1%8D%D1%82%D0%BE,%D0%BC%D0%B0%D1%82%D0%B5%D0%BC%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D1%85%20%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B9%20%D0%B8%D1%85%20%D0%BF%D1%80%D0%BE%D1%81%D1%82%D0%BE%20%D0%BD%D0%B5%D1%82!

**level 4:** 

- Simple example of program


# 26. Request parameters and JSON (required level 2)

**level 1:**  

- [Clone objects with JSON methods;](https://www.samanthaming.com/tidbits/70-3-ways-to-clone-objects/)
  - Spread operators - const cloneObj = { ...someObj }; - shalow copy
  - Object.assign - Object.asign({}, someObj) - shalow copy;
  - JSON - const cloneObj = JSON.parse(JSON.stringify(someObj)); - deep copy

**level 2:**  

- How to add request body
  - https://ru.hexlet.io/courses/http_protocol/lessons/body/theory_unit

```
var xhr = new XMLHttpRequest();
xhr.open('POST', '/submit', true);

xhr.setRequestHeader('Content-Type', 'multipart/form-data; boundary=' + boundary);

xhr.onreadystatechange = function() {
  if (this.readyState != 4) return;

  alert( this.responseText );
}

xhr.send(body);
```

**level 3:** 

- [How to send requests with different content types and what is it for](https://learn.javascript.ru/xhr-forms)
  В стандартных HTTP-формах для метода POST доступны три кодировки, задаваемые через атрибут enctype:   
    - application/x-www-form-urlencoded
    - multipart/form-data
    - text/plain   
> У форм есть две основные кодировки: application/x-www-form-urlencoded – по умолчанию и multipart/form-data – для POST запросов, если явно указана в enctype. Вторая > кодировка обычно используется для больших данных и только для тела запроса.
> Для составления запроса в application/x-www-form-urlencoded используется функция encodeURIComponent.
> Для отправки запроса в multipart/form-data – объект FormData.
> Для обмена данными JS ↔ сервер можно использовать и просто JSON, желательно с указанием кодировки в заголовке Content-Type.

** level 4:**  

- Read the response that came from the back-end and process it;
  - Fetch()
    - response.text() – читает ответ и возвращает как обычный текст,
    - response.json() – декодирует ответ в формате JSON,
    - response.formData() – возвращает ответ как объект FormData (разберём его в следующей главе),
    - response.blob() – возвращает объект как Blob (бинарные данные с типом),
    - response.arrayBuffer();  
    - response.body – это объект ReadableStream, с помощью которого можно считывать тело запроса по частям. 

    - Заголовки ответа модно получить - response.headers.get('Content-Type'))
- how to save the file, how to filter out unnecessary data before using it in the target function; 
  - https://learn.javascript.ru/xmlhttprequest


# 27. Angular.Component (required level x)

**level 1:**  

- What is a component? - Компонент (Angular component) - обособленная часть функционала со своей логикой, HTML-шаблоном и CSS-стилями.
Класс становится Angular компонентом, если его объявлению предшествует декоратор @Component() с объектом конфигурации.
- What metadata are we passing to @Component?
  selector:    'app-hero-list',
  templateUrl: './hero-list.component.html',
  styleUrls: ['./row-card.component.scss']
  providers:  [ HeroService ]
  
- What is Directive; - это компоенент без шаблона
  - С собственным шаблоном, или по-другому компоненты (компоненты являются директивами);
  - Структурные, которые изменяют структуру DOM-дерева; ( **ngIf, **ngFor, **ngSwitch)
  - Атрибуты, которые изменяют внешний вид или поведение по умолчанию элемента DOM-дерева.

**level 2:**  

- Component life cycles;
- What's the difference between component and directive;

**level 3:**  

- How can you transfer data between components?
- What is the minimum definition of a component;
  Создать class, export его, функция декортатор @Component({selector:'', templateUrl: ''})

**level 4:** 

- Dynamic component;
- Create custom directive;

# 28. Angular.Module (required level x)

**level 1:**  

- Angular имеет модеульную архитектуру, в отличии от React(компонентную). Масшиабиаемость 
  
  Для создания отдетного модуля создаем файл .module.ts в ктором @NgModule  - декортатор и класс.
  
```
@NgModule({
  declarations: [
    AppComponent,
    AboutComponent,
    HomeComponent,
    PostsComponent
  ],
  imports: [
    BrowserModule,
    AppRoutingModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```
  
  - declorations: - это массив где решистрируются все компоненты, директивы и пайрыж
  - imports: - это массив, куда импартируются другие модули(BrowserModule? FormsModule, свои созданные модули;
  - exports - подмножество объявлений, которые должны быть видны и использоваться в шаблонах компонентов других модулей NgModules.
  - providers - это массив , где регистриуются сервисыж
  - bootstrap - для главного компонента приложения (точка входа).
  
  Для общих сущностей которые используются в разных модулях создается отдельный модуль(обычно в папке shared). Сущности заносятся в declorations (массив) и возвращаются в exports (массив). Затем в imports (массиве) зарегестрировать shared модуль app. и др.
  
  Метод forRoots(routes) - только для app.module;
  Метод forChild(routes) - используется для остальных модулей приложения при маршрутизации.
  
  Для оптимизации и декомпозирования элементов.
  
  Lasy loading - отложенная загрузка.
  
  При работе с разбивкой на модули есть возможность разбивики на части (на chunks). Позволит загружать сначала необходимый для рендеринга компоненет, а при переходе будет загружать тоже необходимый компонет(chunk)
  
  В  app-routing.module.ts доббваить объект с path: '...' и loadChildren: 'link#classModule(класс модуля)'. Новый синтаксиси позволяет передовать функцию (стрелочную):
  
  ```
  loadChildren: () => import('link').then(m => m.AboutPageModule)
  ```
  
  ***Изменить стратегию загрузки*** в app.modile.ts необходимо в app.module.ts
  
  ```
  imports: [
    RouterModule.forRout(routes),
    {preLoadingStrategy:PreloadingAllModules (или noPreloading)}
  ]
  ```
  
Это позволяет изменить загрузку компонентов. В первую очередь загрузятся все необходимые компоеннеты для рендеринга, а после все остальные (для роутинга). Что бы можно было перехолдить через ссылки без перезагрузок.

**level 2:**  

- What is your understanding of the Module structure?
- Why are modules needed?

**level 3:**  

- For what import/export/declaration/providers

**level 4:**  

- Types of modules 
  - модули страниц;
  -  модули сервисов;
  -  модули компонентов для многократного использования (shared).


# 29. Angular. Service (required level 4)

**level 1:**  

- What is @Inject()?

**level 2:**  

- What is @Injectable()?

**level 3:**  

- List of hierarchies (Module, Elements and Platform)

**level 4:** 

- What is DI tree and how Angular look for nessesssary dependency;
- ProvideIn  what benefits of using it;


# 30. Angular. Data binding (required level 4)

**level 1:**  

- What is data binding;
- Categories of data binding;

**level 2:**  

- Class/style, attribute binding

**level 3:**  

- Attribute binding

**level 4:**  

- How do I create a two-way data binding manually?



