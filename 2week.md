[be back](https://github.com/ToMikhail/andersen)
# 9. Classes (required level 3)
## level 1:  
- [Basic syntax;](https://learn.javascript.ru/class#sintaksis-class)
## level 2:  
- [Inheritance;](https://learn.javascript.ru/class-inheritance)
## level 3:  
- [Private and protected properties and methods;](https://learn.javascript.ru/private-protected-properties-methods)
## level 4:  
- ["instanceof" usage;](https://javascript.info/instanceof) 
- [Static properties and methods;](https://javascript.info/static-properties-methods)

# 10. [Asynchronous programming (required level 4)](https://developer.mozilla.org/ru/docs/Learn/JavaScript/Asynchronous)
## level 1:  
- [Blocking code;]([https://learn.javascript.ru/event-loop](https://nodejs.org/ru/docs/guides/blocking-vs-non-blocking/#:~:text=%D0%9E%20%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8%20%D0%B3%D0%BE%D0%B2%D0%BE%D1%80%D1%8F%D1%82%2C%20%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0%20%D0%B2%D1%8B%D0%BF%D0%BE%D0%BB%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5,%D1%82%D0%B0%D0%BA%20%D0%BA%D0%B0%D0%BA%20%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82%20%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D1%80%D1%83%D1%8E%D1%89%D0%B0%D1%8F%20%D0%BE%D0%BF%D0%B5%D1%80%D0%B0%D1%86%D0%B8%D1%8F.)
## level 2:  
- [Event loop concept;](https://learn.javascript.ru/event-loop)
- [setTimeout](https://developer.mozilla.org/ru/docs/Web/API/setTimeout), [setInterval](https://developer.mozilla.org/ru/docs/Web/API/setInterval). [Why do we need them?](https://learn.javascript.ru/settimeout-setinterval)
- [Clear timeouts and intervals;](https://developer.mozilla.org/ru/docs/Web/API/clearTimeout) - (https://www.youtube.com/watch?v=vIZs5tH-HGQ)
## level 3:  
- [Zero delays and event loop queue (setTimeout(() => {}, 0));]
## level 4:  
- [Macro and micro tasks (basic understanding);](https://learn.javascript.ru/event-loop)

# 11. Promise, async/await (required level 3)
## level 1:  
- -
## level 2:  
- [Promises vs callbacks;](https://qna.habr.com/q/468150)
- [Examples of async functions;](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function)
## level 3:  
- [States of promises;] 
  - fulfilled: Action related to the promise succeeded.
  - rejected: Action related to the promise failed.
  - pending: Promise is still pending i.e. not fulfilled or rejected yet.
  - settled: Promise has fulfilled or rejected.
- [Finally;](https://learn.javascript.ru/promise-basics#ochistka-finally)
- [Exceptions/errors handling;](https://learn.javascript.ru/promise-basics#potrebiteli-then-catch)
## level 4:  
- [How to use then to catch errors;](https://learn.javascript.ru/promise-basics#potrebiteli-then-catch)
- [Exceptions/errors handling;]
- [Rewriting Promise code with async/await;](https://learn.javascript.ru/task/rewrite-async)

# 12. Error handling (required level 3)
## level 1:  
- -
## level 2:  
- -
## level 3:  
- [try catch usage](https://learn.javascript.ru/try-catch)
## level 4:  
- [exceptions throwing](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Statements/throw) 

# 13. Work with backend (required level 4)
## level 1:  
- [what is https;](https://developer.mozilla.org/ru/docs/Glossary/https)
- [what is status codes;](https://developer.mozilla.org/ru/docs/Web/HTTP/Status)
- [what is AJAX;](https://developer.mozilla.org/ru/docs/Web/Guide/AJAX) - [fetch(video)](https://www.youtube.com/watch?v=eKCD9djJQKc)
- [what is JSON;](https://habr.com/ru/post/554274/)
## level 2:  
- [Basic usage of XHR (how to make simple request and handle answer);
response code groups](https://learn.javascript.ru/xmlhttprequest) - (https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest)
- [Basic usage of fetch() (how to make simple request and handle answer);](https://developer.mozilla.org/ru/docs/Web/API/Fetch_API/Using_Fetch)
## level 3:  
- CRUD HTTP methods;(https://proglib.io/p/chto-takoe-api-i-crud-prostymi-slovami)
- What is REST?(https://www.google.com/search?q=rest+%D1%87%D1%82%D0%BE+%D1%8D%D1%82%D0%BE&sxsrf=ALiCzsZBfdTGPrZsSpwXU8fD02Jyxn8g6w%3A1668510988213&ei=DHVzY6zJDI_IrgSlkZTIDQ&ved=0ahUKEwis_4Xmh7D7AhUPpIsKHaUIBdkQ4dUDCA8&uact=5&oq=rest+%D1%87%D1%82%D0%BE+%D1%8D%D1%82%D0%BE&gs_lcp=Cgxnd3Mtd2l6LXNlcnAQAzIGCAAQBxAeMgYIABAHEB4yBggAEAcQHjIFCAAQgAQyBggAEAcQHjIGCAAQBxAeMgYIABAHEB4yBggAEAcQHjIGCAAQBxAeMgYIABAHEB46BQgAEKIEOggIABAHEB4QCjoICAAQBxAeEA86CAgAEAgQBxAeOgkIABAHEB4QiwNKBAhNGAFKBAhBGABKBAhGGABQAFjxGWDUG2gDcAF4AIABhwGIAYMHkgEDOC4ymAEAoAEBuAECwAEB&sclient=gws-wiz-serp)
- CORS what is it, why do we need them(https://developer.mozilla.org/ru/docs/Web/HTTP/CORS)
- Difference between PUT, PATCH, POST;(https://proglib.io/p/chto-takoe-api-i-crud-prostymi-slovami)
## level 4:  
- What is CORS and why we need it;(https://habr.com/ru/company/macloud/blog/553826/)
- Work with json responce;(https://developer.mozilla.org/en-US/docs/Web/API/Response/json)
- Set headers in request;(https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest/setRequestHeader)
- How to get around CORS;() - ???????????

# 14. Request parameters and JSON (required level 2)
## level 1:  
- [Clone objects with JSON methods;](https://www.samanthaming.com/tidbits/70-3-ways-to-clone-objects/)
## level 2:  
- [How to add request body]()(https://ru.hexlet.io/courses/http_protocol/lessons/body/theory_unit)
## level 3:  
- [How to send requests with different content types and what is it for]()
## level 4:  
- [Read the response that came from the back-end and process it (how to save the file, how to filter out unnecessary data before using it in the target function);]() 

# 15. Garbage collector (required level x)
## level 1:  
- -
## level 2:  
- -
## level 3:  
- -
## level 4:  
- [What is garbage collector?]()
- [Why do we need it?]()

# 16. Regular Expressions, RegExp (required level x)
## level 1:  
- [What is RegExp]()
- [How to use RegExp]()
## level 2:  
- [Two methods of RegExp object;]()
## level 3:  
- [Two ways to create RegExp;]()
## level 4:  
- [Basic RegExp pattern (character classes);]()

# 17. DOM (required level 3)
## level 1:  
- -
## level 2:  
- [- What is the DOM?]()
## level 3:  
- [What is DOM tree?]()
## level 4:  
- [DOM inspecting (live DOM viewer);]() 


