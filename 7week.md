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
  ```
    options: {
    headers?: HttpHeaders | {[header: string]: string | string[]}, - какую часть ответа следует вернуть
    observe?: 'body' | 'events' | 'response', - какую часть ответа следует вернуть
    params?: HttpParams|{[param: string]: string | number | boolean | ReadonlyArray<string | number | boolean>},
    reportProgress?: boolean,
    responseType?: 'arraybuffer'|'blob'|'json'|'text',
    withCredentials?: boolean,
    }
   ```
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
  ```
  this.http.get(filename, {responseType: 'text'})
  ```

**level 4:**  

- Adding and updating headers;
  - https://angular.io/guide/http#adding-and-updating-headers
  >Многие серверы требуют дополнительных заголовков для операций сохранения. Например, серверу может потребоваться токен авторизации или заголовок «Content-Type», чтобы явно объявить MIME-тип тела запроса.    
  
  ***Adding headers***
  
  ```
  const httpOptions = {
    headers: new HttpHeaders({
      'Content-Type':  'application/json',
      Authorization: 'my-auth-token'
    })
  };
  ```
  
  ***Updating headers***
  >Вы не можете напрямую изменить существующие заголовки в предыдущем объекте параметров, поскольку экземпляры класса HttpHeaders являются неизменяемыми. Вместо этого используйте метод set(), чтобы вернуть клон текущего экземпляра с примененными новыми изменениями.
  ```
  httpOptions.headers =
  httpOptions.headers.set('Authorization', 'my-new-auth-token');
  ```


---

# 43. Angular. HTTP interceptors (required level 2)   

https://angular.io/guide/http#intercepting-requests-and-responses
>Angular HTTP Interceptor позволяет перехватывать HTTP-запросы перед их отправкой и вносить в них необходимые изменения. То же самое справедливо и для ответов сервера. Вы объявляете перехватчики, которые проверяют и преобразовывают HTTP-запросы из вашего приложения на сервер. Те же перехватчики также могут проверять и преобразовывать ответы сервера на обратном пути к приложению. Несколько перехватчиков формируют прямую и обратную цепочку обработчиков запросов/ответов.

>Наиболее частое их применение — отправка авторизационных данных, логирование и обработка серверных ошибок.

>Создание сервиса начинается с внедрения интерфейса Angular HttpIntrceptor из @angular/common/http и реализации его метода intercept(). intercept() модифицирует исходный запрос и возвращает объект Observable события HttpEvent<any>, который в свою очередь возвращает метод next() объекта типа HttpRequest.

**level 1:**  
-

**level 2:**  

- Request body modifying/cloning (interceptors)
  
  ```
    export class NoopInterceptor implements HttpInterceptor {

      intercept(req: HttpRequest<any>, next: HttpHandler): Observable<HttpEvent<any>> {
  
        const cloned = req.clone( { 
           headers: req.headres.append('Auth': 'some_randon_token'))
           }
  
        return next.handle(cloned).pipe(
          .tap((event) => {
            if(event.type === HTTPEventType.Response) {
              console.log(event);
            }
          }));
        }
      }
  ```

**level 3:**  

- Providing for interceptors
  - https://angular.io/guide/http#provide-the-interceptor
  
  >NoopInterceptor — это служба, управляемая системой внедрения зависимостей (DI) Angular. Как и другие службы, вы должны предоставить класс перехватчика, прежде чем приложение сможет его использовать. Поскольку перехватчики являются необязательными зависимостями службы HttpClient, их необходимо предоставлять в том же инжекторе или родительском инжекторе, который предоставляет HttpClient. Перехватчики, предоставляемые после того, как DI создает HttpClient, игнорируются.

**level 4:**  

- How to implement authorization via interceptor
  - https://angular.io/guide/http#http-interceptor-use-cases
  
    ```
      export class AuthInterceptor implements HttpInterceptor {

        constructor(private auth: AuthService) {}

        intercept(req: HttpRequest<any>, next: HttpHandler) {
          // Get the auth token from the service.
          const authToken = this.auth.getAuthorizationToken();

          // Clone the request and replace the original headers with
          // cloned headers, updated with the authorization.
          const authReq = req.clone({
            headers: req.headers.set('Authorization', authToken)
          });

          // send cloned request with header to the next handler.
          return next.handle(authReq);
        }
      }
  ```
---

# 44. Angular. HTTP. Errors & Retrying (required level 3)

**level 1:**  

-

**level 2:**
-

**level 3:**  

- Request retrying
  - https://angular.io/guide/http#retrying-a-failed-request
  >Иногда ошибка носит временный характер и автоматически исчезает при повторной попытке. Например, в мобильных сценариях часто случаются сбои в сети, и повторная попытка может дать успешный результат. Библиотека RxJS предлагает несколько операторов повтора. Например, оператор retry() автоматически повторно подписывается на неудавшийся Observable заданное количество раз. Повторная подписка на результат вызова метода HttpClient приводит к повторной отправке HTTP-запроса. В следующем примере показано, как передать неудачный запрос оператору retry() перед его передачей обработчику ошибок.
  ```
    getConfig() {
    return this.http.get<Config>(this.configUrl)
      .pipe(
        retry(3), // retry a failed request up to 3 times
        catchError(this.handleError) // then handle the error
      );
    }
  ```

**level 4:** 

- Request aborting
  
  unsibscribe()

---

# 45. TypeScript. Basic (required level 4)

**level 1:**  

- Basic types provided by TS (void, never, unknown, Tulip, etc.)
  - string
  - number
  - boolean
  - array - let arr: number[](let arr: Array<number>)
  - tuple - может содержать два значения разных типов данных. - let tuple: [number, string] = [123, 'string']
  - enum - позволяют нам объявить набор именованных констант, то есть набор связанных значений, которые могут быть числовыми или строковыми значениями.
  ```
    enum PrintMedia {
      Newspaper,
      Newsletter,
      Magazine,
      Book
    }
  ```
  - union - позволяет нам использовать более одного типа данных для переменной или параметра функции. Это называется союзным типом. let code: (string | number);
  - any - let something: any = "Hello World!"; 
  - void - используется там, где нет данных. Например, если функция не возвращает никакого значения, вы можете указать тип возвращаемого значения void. Нет смысла присваивать значение void переменной, так как значение void может быть присвоено только null или undefined.
  ```
  let nothing: void = undefined;
  let num: void = 1; // Error
  ```
  - never - который указывает значения, которые никогда не возникнут. используется, когда вы уверены, что что-то никогда не произойдет. Например, вы пишете функцию, которая не возвращается в конечную точку или всегда выдает исключение.
  ```
    function throwError(errorMsg: string): never { 
              throw new Error(errorMsg); 
    } 

    function keepProcessing(): never { 
                while (true) { 
             console.log('I always does something and never ends.')
         }
    }
  ```
  >Тип void может иметь undefined или null в качестве значения, где as never не может иметь никакого значения.
  В TypeScript функция, которая не возвращает значение, на самом деле возвращает значение undefined. Рассмотрим следующий пример.
  
  - unknow - unknown, который является типобезопасным аналогом any. Неизвестному можно присвоить что угодно, но неизвестное нельзя присвоить ничему, кроме самого себя и любого без утверждения типа или сужения на основе потока управления. Точно так же никакие операции над неизвестным не допускаются без предварительного утверждения или сужения до более конкретного типа.
  ```
    let vAny: any = 10;          // We can assign anything to any
    let vUnknown: unknown =  10; // We can assign anything to unknown just like any 

    let s1: string = vAny;     // Any is assignable to anything 
    let s2: string = vUnknown; // Invalid; we can't assign vUnknown to any other type (without an explicit assertion)

    vAny.method();     // Ok; anything goes with any
    vUnknown.method(); // Not ok; we don't know anything about this variable
  ```
  

**level 2:**  

- Union types - позволяет нам использовать более одного типа данных для переменной или параметра функции. Это называется союзным типом. let code: (string | number);;
- Literal types;
  >В дополнение к общим типам string и number мы можем ссылаться на определенные строки и числа в позициях типа.
  ```
    let x: "hello" = "hello";
  ```

**level 3:**  

- Types casting
  - Casting with as
 ```
  let x: unknown = 'hello';
  console.log((x as string).length);
 ```
  - Casting with <> - Использование <> работает так же, как приведение as.
  ```
    let x: unknown = 'hello';
    console.log((<string>x).length);
  ```

**level 4:**  

- Generics (simple generics, class generics)
  https://www.tutorialsteacher.com/typescript/typescript-generic
  >предоставляют способ заставить компоненты работать с любым типом данных, а не ограничиваться одним типом данных. Generics предоставляют способ заставить компоненты работать с любым типом данных, а не ограничиваться одним типом данных. Таким образом, компоненты могут вызываться или использоваться с различными типами данных.
Чтобы решить эту проблему, TypeScript представил дженерики. Обобщения используют переменную типа <T>, особый тип переменной, которая обозначает типы. Переменная типа запоминает тип, который предоставляет пользователь, и работает только с этим конкретным типом. Это называется сохранением информации о типе.
  ```
    function getArray(items : any[] ) : any[] {
    return new Array().concat(items);
    }

    let myNumArr = getArray([100, 200, 300]);
    let myStrArr = getArray(["Hello", "World"]);

    myNumArr.push(400); // OK
    myStrArr.push("Hello TypeScript"); // OK

    myNumArr.push("Hi"); // OK
    myStrArr.push(500); // OK

    console.log(myNumArr); // [100, 200, 300, 400, "Hi"] // wrong behavior
    console.log(myStrArr); // ["Hello", "World", "Hello TypeScript", 500] // wrong behavior
  ```
  
  ```
    function getArray<T>(items : T[] ) : T[] {
    return new Array<T>().concat(items);
    }

    let myNumArr = getArray<number>([100, 200, 300]);
    let myStrArr = getArray<string>(["Hello", "World"]);

    myNumArr.push(400); // OK
    myStrArr.push("Hello TypeScript"); // OK

    myNumArr.push("Hi"); // Compiler Error
    myStrArr.push(500); // Compiler Error
  ```
---

# 46. TypeScript. Interface (required level 4)

**level 1:**  

- Difference between interface and class;
    - interface:  
      - Описывает, как должен выглядеть объект 
      - Существует только во время компиляции с единственной целью проверки типов  
  ```
    interface IEmployee {
      empCode: number;
      empName: string;
      getSalary: (number) => number; // arrow function
      getManagerName(number): string; 
    }
  ```
    - Class:  
      - Используется в качестве схемы для создания/производства объектов. 
      - Может реализовать интерфейс, что означает, что он должен реализовать как минимум все свойства/методы интерфейса.
- Optional properties;

**level 2:**  

- Readonly properties 
  >- делает свойство доступным только для чтения в классе, типе или интерфейсе. Префикс Readonly используется, чтобы сделать свойство доступным только для чтения. К членам, c Readonly, можно получить доступ за пределами класса, но их значение нельзя изменить. Поскольку члены, Readonly, не могут быть изменены вне класса, их необходимо либо инициализировать при объявлении, либо инициализировать внутри конструктора класса.;
- Modificators (public, protected, private);
  - public - По умолчанию все члены класса в TypeScript являются общедоступными. Все публичные члены доступны в любом месте без каких-либо ограничений.
  - private - Модификатор закрытого доступа гарантирует, что члены класса видны только этому классу и недоступны за пределами содержащего его класса.
  - protected - Модификатор защищенного доступа аналогичен модификатору закрытого доступа, за исключением того, что к защищенным членам можно получить доступ, используя их производные классы.

**level 3:**  

- Function types for interfaces
  ```
    interface IEmployee {
    empCode: number;
    empName: string;
    getSalary: (number) => number; // arrow function
    getManagerName(number): string; 
    }
  ```
  
  ```
    interface KeyValueProcessor
    {
        (key: number, value: string): void;
    };

    function addKeyValue(key:number, value:string):void { 
        console.log('addKeyValue: key = ' + key + ', value = ' + value)
    }

    function updateKeyValue(key: number, value:string):void { 
        console.log('updateKeyValue: key = '+ key + ', value = ' + value)
    }

    let kvp: KeyValueProcessor = addKeyValue;
    kvp(1, 'Bill'); //Output: addKeyValue: key = 1, value = Bill 

    kvp = updateKeyValue;
    kvp(2, 'Steve'); //Output: updateKeyValue: key = 2, value = Steve 
  ```

**level 4:**  

- Abstract class 3. Abstract class vs Interfaces
  >Абстрактные классы представляют классы, определенные с ключевым словом abstract. Они во многом похожи на обычные классы за тем исключением, что мы не можем создать напрямую объект абстрактного класса, используя его конструктор.
  ```
    abstract class Figure {
    }
  ```
  >Как правило, абстрактные классы описывают сущности, которые в реальности не имеют конкретного воплощения. Например, геометрическая фигура может представлять круг, квадрат, треугольник, но как таковой геометрической фигуры самой по себе не существует. Есть конкретные фигуры, с которыми мы и работаем. В то же время все фигуры могут иметь какой-то общий функционал. В этом случае мы можем определить абстрактный класс фигуры, поместить в него общий функционал, и от него унаследовать классы конкретных геометрических фигур:
  
  >Интерфейсы поддерживают множественное наследование. Абстрактный класс не поддерживает множественное наследование. Интерфейс TypeScript не содержит кода JavaScript, что означает, что он доступен только в TypeScript и не создает никакого кода в скомпилированном файле JavaScript. Абстрактный класс компилируется в функции JavaScript.
  
  >Abstract class — это и контракт, и реализация фабрики. Абстрактный класс также является реализацией, но неполной. В частности, абстрактный класс существует во время выполнения, даже если он имеет только абстрактные методы (тогда можно использовать instanceof).  
  >Interface — это контракт, который определяет свойства и то, что может делать реализующий их объект.

---

# 47. TypeScript. Functions (required level 4)

**level 1:**  

- Typing the function
  - Named Functions
  ```
    function Sum(x: number, y: number) : number {
      return x + y;
    }
  ```
  - Anonymous Function
  ```
    let Sum = function(x: number, y: number) : number
    {
        return x + y;
    }
  ```
  - Arrow func
  ```
    let sum = (x: number, y: number): number => {
      return x + y;
    }
  ```

**level 2:**  

- Rest params in function typing - Когда количество параметров, которые получит функция, неизвестно или может варьироваться, мы можем использовать остальные параметры. В JavaScript это достигается с помощью переменной «arguments». Однако с TypeScript мы можем использовать оставшийся параметр, обозначенный многоточием.... В параметр rest мы можем передать ноль или более аргументов. Компилятор создаст массив аргументов с предоставленным нами именем параметра rest.В параметр rest мы можем передать ноль или более аргументов. Компилятор создаст массив аргументов с предоставленным нами именем параметра rest.
  ```
    function Greet(greeting: string, ...names: string[]) {
      return greeting + " " + names.join(", ") + "!";
    }

    Greet("Hello", "Steve", "Bill"); // returns "Hello Steve, Bill!"

    Greet("Hello");// returns "Hello !"
  ```
>Помните, что rest параметры должны быть последними в определении функции, иначе компилятор TypeScript покажет ошибку. Следующее недействительно.
  
**level 3:**  
- Default params
  >Параметры — это значения или аргументы, передаваемые функции. В TypeScript компилятор ожидает, что функция получит точное количество и тип аргументов, как указано в сигнатуре функции. Если функция ожидает три параметра, компилятор проверяет, что пользователь передал значения для всех трех параметров, т. е. проверяет точные совпадения. Это отличается от JavaScript, где допустимо передавать меньше аргументов, чем ожидает функция. Параметры, которые не получают значения от пользователя, считаются неопределенными.
  
  ```
    function applyDiscount(price, discount = 0.05) {
      return price * (1 - discount);
    }

    console.log(applyDiscount(100)); // 95
  ```

**level 4:**  

- Rest operator for function parameters;
- Optional params for functions;
  >Параметры, которые могут получить или не получить значение, могут быть добавлены с помощью '?' чтобы пометить их как необязательные. Все необязательные параметры должны следовать за обязательными параметрами и должны быть в конце.
  ```
    function Greet(greeting: string, name?: string ) : string {
      return greeting + ' ' + name + '!';
    }
  ```


---

