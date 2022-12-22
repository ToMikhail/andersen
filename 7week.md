[be back](https://github.com/ToMikhail/andersen)




# 42. Angular. HTTP. Request options (required level 4)

***HttpClient***
  
  Общение" с сервером Angular осуществляет через REST-подобные запросы. За это отвечает HttpClientModule.  
  В компонент или сервис (в зависимости от построения архитектуры) импортируется сервис HttpClient.  
  For example:
  ```
  @Injectable()
export class DataService {
  constructor(private http: HttpClient) {}
}
  ```
  
***Методы HTTP запросов***
  
  В архитектуре REST API используются разные методы HTTP запросов. Основные:
  - GET - используется для получения данных с сервера
  - POST - используется для создания новой записи
  - PUT - используется для  обновдления существуюшей записи;
  - DELETE -  используется для удаления записи.
  
  >Все методы сервиса HttpClient возвращают тип ***Observable*** это означает, что если при вызове метода, который должен сделать HTTP-запрос, не вызвать метод subscribe(), то ничего не произойдет. Методу subscribe() можно передавать две функции-обработчика, первая выполнится в случае успешного ответа от сервера, вторая - в случае ошибки.

**level 1:**  
-

**level 2:**  

- List of configs that can be passed in options;
    options: {
    headers?: HttpHeaders | {[header: string]: string | string[]},
    observe?: 'body' | 'events' | 'response',
    params?: HttpParams|{[param: string]: string | number | boolean | ReadonlyArray<string | number | boolean>},
    reportProgress?: boolean,
    responseType?: 'arraybuffer'|'blob'|'json'|'text',
    withCredentials?: boolean,
    }
- Errors handling;
  ***Обработка ошибок***  
  При работе с HttpClient есть можество путей обработать ошибку.
  - 1 способ. У метода subscribe(callback1 - удачный ответ с сервера(response); *callback2 - возращает ошибку, где мы ее можем обработать:* callback3 - когда stream  закончился). =>
  ```
  http.get('link').subscribe(res => {}, error => {})
  ```
  - 2 способ. Передать в методе pipe(catchError(err => {return throwError(error)}))
  ```
  return http('link').pipe(catchError(err => { return throwError(error) }))
  ```

**level 3:**  

- Requesting non-JSON data

**level 4:**  

- Adding and updating headers;

---

# 43. Angular. HTTP. HTTP interceptors (required level 2)

**level 1:**  
-

**level 2:**  

- Request body modifying/cloning (interceptors)

**level 3:**  

- Providing for interceptors

**level 4:**  

- How to implement authorization via interceptor
---

# 44. Angular. HTTP. Errors & Retrying (required level 3)

**level 1:**  

-

**level 2:**
-

**level 3:**  

- Request retrying

**level 4:** 

- Request aborting

---

# 45. TypeScript. Basic (required level 4)

**level 1:**  

- Basic types provided by TS (void, never, unknown, Tulip, etc.)

**level 2:**  

- Union types;
- Literal types;

**level 3:**  

- Types casting

**level 4:**  

- Generics (simple generics, class generics)

---

# 46. TypeScript. Interface (required level 4)

**level 1:**  

- Difference between interface and class;
- Optional properties;

**level 2:**  

- Readonly properties;
- Modificators (public, protected, private);

**level 3:**  

- Function types for interfaces

**level 4:**  

- Abstract class 3. Abstract class vs Interfaces

---

# 47. TypeScript. Functions (required level 4)

**level 1:**  

- Typing the function

**level 2:**  

- Rest params in function typing

**level 3:**  
- Default params

**level 4:**  

- Rest operator for function parameters;
- Optional params for functions;


---

# 00. Angular. Testing. Unit (required level 3)

**level 1:**  
-

**level 2:**  

- Test bed. Why do we need it?

**level 3:**  

- Testing components/services

**level 4:** 

- Testing directives;
- Testing pipes;

---

# 00. Angular. Extra. AoT / JIT (required level 2)

**level 1:**  
-

**level 2:**  
-

**level 3:**  

- Basic difference for both compilations

**level 4:**  

- Template build for AoT;
- AoT compilation phases;


---

# 00. Angular. Extra. External tools (required level 2)

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

# 00. Common. Patterns. Design Patterns (Factory, Module, Prototype, Observer, Builder, Facade, Decorator) (required level 4)

**level 1:**  
-

**level 2:**  

- Understanding what programming patterns are and what problem they solve

**level 3:**  

- Subtypes of programming patterns, name a few examples of each

**level 4:** 

- Fasad, Observer, Factory - be able to write

---

# 00. Common. Debugging. App speed estimation, app debugging (required level 2)

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
