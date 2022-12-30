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

**level 1:**  
-

**level 2:**  
-

**level 3:**  

- Basic difference for both compilations
  - https://www.geeksforgeeks.org/what-is-aot-and-jit-compiler-in-angular/

**level 4:**  

- Template build for AoT;
- AoT compilation phases;
  1.	code analysis
  2.	code generation
  3.	template type checking

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

