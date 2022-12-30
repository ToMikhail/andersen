[be back](https://github.com/ToMikhail/andersen)


# 48. Angular. Testing. Unit (required level 3)

**level 1:**  
-

**level 2:**  

- Test bed. Why do we need it?
> является основным API для написания модульных тестов для приложений и библиотек Angular. Настраивает и инициализирует среду для модульного тестирования и предоставляет методы для создания компонентов и служб в модульных тестах.   
> Как один из метод решения проблемы тестов компонента с зависимостями. TestBed - это инструмент от Anguar, кторый создает тестовое окружение (тестовый модуль).
TestBed

   * 1-й вариант замокать зависимость   
 > Kак вариант сделать заглушку зависимости, это создание объекта и передать туда методы для зависимости и добавить это все в TestBed.ConfigureTestingModule  
  ```
  TestBed.ConfigureTestingModule (
  { provieder: [TestingService], 
    { provide: FirstDepService, useValue: fakeObj }
  ```
  * 2-й вариант замокать зависимость 
 > Создать в fakeObj метод через jasmine.createSpy()   
  ```
  const fakeObj = {
    returnValue: jasmine.createSpy('returnSpy')
  }
  ```
  
   * 3-й вариант замокать зависимость(самый удобный и быстрый способ)
 > Создать в fakeObj метод через jasmine.createSpyObject() и добавить fakeObj в useValue в TestBed.ConfigureTestingModule
  ```
  const fakeObj = jasmine.createSpyObject(массив с названеим методов с необходимыми зависимостями)
  ```

**level 3:**  

- Testing components/services
   - https://angular.io/guide/testing-components-scenarios
   - https://angular.io/guide/testing-services

  > В компоненте необходимо тестировать шаблон и сам класс.   
  > В шаблон необходимо тестировать какие то сложные вещи (контен не надо!), привязку данных, тестирование директив   
  > Что бы получить доступ к элментоу DOM, необбходимо использовать ***debugElemen.querry(By.css('h1'))***   
  > В классе компонента необходимо тесчтировать все public methods, private methods -тестировать не надо. Но если возникает такая необходимость то сделать метод не private a public.

**level 4:** 

- Testing directives;
  - https://angular.io/guide/testing-attribute-directives
  
- Testing pipes;
  - https://angular.io/guide/testing-pipes

---

# 49. Angular. Extra. AoT / JIT (required level 2)
  
  - https://angular.io/guide/aot-compiler
  - https://angdev.ru/doc/angular-compilation/

**level 1:**  
-

**level 2:**  
-

**level 3:**  

- Basic difference for both compilations
  - https://www.geeksforgeeks.org/what-is-aot-and-jit-compiler-in-angular/
>Поскольку разработка ведется на TypeScript, то для запуска в браузере приложение должно быть предварительно обработано компилятором Angular, который конвертирует код исходных файлов в исполняемый JavaScript.
>Механизм Angular compile реализован в двух режимах:

    - JIT-компиляция (Just-in-TIme);
    - AOT-компиляция (Ahead-of-Time).
    
>В режиме JIT (используется по умолчанию) приложение компилируется в момент его запуска в браузере. В режиме AOT компиляция происходит в момент сборки приложения. Для этого при выполнении некоторых CLI-команд необходимо указать флаг --aot. 
>При сборке приложения с флагом --prod AOT-компиляция используется по умолчанию.

  Преимущества Angular AOT:
    - Быстрая загрузка в браузере. Меньше времени тратится за счет того, что:    
    - Приложение компилируется до загрузки в браузер;    
    - В сборку не включается компилятор Angular и, как следствие, конечные файлы имеют меньший размер;    
    - Выполняется меньше AJAX-запросов на получение исходных HTML- и CSS-файлов, поскольку они включаются в строковом виде в файлы JavaScript.   
    - Обнаружение ошибок при сборке. Имеется возможность исправить все ошибки до запуска приложения в режиме эксплуатации.    
    - Повышенная безопасность.Поскольку HTML- и CSS-файлы включаются в процессе Angular compile в файлы JavaScript, то нет возможности просмотреть шаблоны, что снижает риск осуществления атак.

**level 4:**  

- Template build for AoT;
- AoT compilation phases:  

    * Code analysis (Анализ) - В процессе анализа формируются данные, необходимые для генерации кода. Это файлы определения типов (*.d.ts) и файлы, содержащие информацию о метаданных, указанных в декораторах (*.metadata.json). Также процесс анализа включает в себя некоторую оптимизацию кода.
    * Code generation (Генерация кода) - На этой стадии интерпретируются все файлы, сгенерированные на стадии анализа. Отдельно стоит упомянуть проверку модификаторов доступа свойств классов. Например, если свойство определено как private и используется в шаблоне, то будет сгенерирована соответствующая ошибка.
    *	Template type checking (Валидация) - На стадии валидации компилятор шаблонов использует компилятор TypeScript для проверки правильности использования свойств и методов компонентов и сервисов в шаблонах.

---

# 50. Angular. Extra. External tools (required level 2)

https://ngrx.io/docs

**level 1:**  
-

**level 2:**  
-

**level 3:**  
- tslinter/eslinter. Angular and rxjs main linter rules

**level 4:** 
- Lighthouse. 
- List of sections(Performance, accessibility, etc.) and short define

---

# 51. Common. Patterns. Design Patterns (Factory, Module, Prototype, Observer, Builder, Facade, Decorator) (required level 4)

**level 1:**  
-

**level 2:**  

- Understanding what programming patterns are and what problem they solve

**level 3:**  

- Subtypes of programming patterns, name a few examples of each

**level 4:** 

- Fasad, Observer, Factory - be able to write

---

# 52. Common. Debugging. App speed estimation, app debugging (required level 2)

**level 1:**  

- -Basic understanding of debugging process;

**level 2:**  

- Web-browser console usage;
- Work with breakpoints, types of  breakpoints;

**level 3:**  

- Networking, Google Lighthouse, redux devtools

**level 4:** 

- How we can measurement of speed of application

---

