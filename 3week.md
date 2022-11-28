[be back](https://github.com/ToMikhail/andersen)

# 18. Work with backend (required level 4)
## level 1:  
- [what is https;](https://developer.mozilla.org/ru/docs/Glossary/https)
- [what is status codes;](https://developer.mozilla.org/ru/docs/Web/HTTP/Status)
- [what is AJAX;](https://developer.mozilla.org/ru/docs/Web/Guide/AJAX)
- [what is JSON;](https://habr.com/ru/post/554274/)
  - (https://tproger.ru/articles/chto-takoe-json-vvedenie/)
## level 2:  
- [Basic usage of XHR, how to make simple request and handle answer) response code groups](https://learn.javascript.ru/xmlhttprequest) 
  - (https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest)
  - [video.Minin.serverRequests](https://www.youtube.com/watch?v=eKCD9djJQKc)
- [Basic usage of fetch() (how to make simple request and handle answer);](https://developer.mozilla.org/ru/docs/Web/API/Fetch_API/Using_Fetch)
  - (https://learn.javascript.ru/fetch)
  - [fetch(video)](https://www.youtube.com/watch?v=eKCD9djJQKc)
## level 3:  
- CRUD HTTP methods;(https://proglib.io/p/chto-takoe-api-i-crud-prostymi-slovami)
- [What is REST?](https://medium.com/@andr.ivas12/rest-%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%8B%D0%BC-%D1%8F%D0%B7%D1%8B%D0%BA%D0%BE%D0%BC-90a0bca0bc78)
  - https://habr.com/ru/post/38730/
- CORS what is it -  Cross-Origin Resource Sharing («совместное использование ресурсов между разными источниками») -  механизм, использующий дополнительные HTTP-заголовки, чтобы дать возможность агенту пользователя получать разрешения на доступ к выбранным ресурсам с сервера на источнике (домене), отличном от того, что сайт использует в данный момент. Говорят, что агент пользователя делает запрос с другого источника (cross-origin HTTP request), если источник текущего документа отличается от запрашиваемого ресурса доменом, протоколом или портом.
- why do we need CORS 
  - (https://developer.mozilla.org/ru/docs/Web/HTTP/CORS)
  - (https://learn.javascript.ru/fetch-crossorigin#zachem-nuzhen-cors-ekskurs-v-istoriyu)
- Difference between PUT, PATCH, POST;(https://proglib.io/p/chto-takoe-api-i-crud-prostymi-slovami)
## level 4:  
- What is CORS and why we need it;(https://habr.com/ru/company/macloud/blog/553826/)
- Work with json responce;(https://developer.mozilla.org/en-US/docs/Web/API/Response/json)
- Set headers in request;(https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest/setRequestHeader)
- How to get around CORS;() - https://developer.mozilla.org/ru/docs/Web/HTTP/Headers/Access-Control-Allow-Origin

# 18. Development methodologies (agile and beyond) (required level 2)
## level 1:  
- Why do we need metodology in our team;
- definition of agile;
## level 2:  
- Definition of scrum and kanban. Base concept;  
  - SCRUM -  это набор правил для организации гибкого рабочего процесса, который заключается в командном подходе, работе итерациями, фокусировке на цели каждой итерации и нестандартном распределении обязанностей внутри коллектива.
  - Kanban — Методика предполагает обсуждение производительности в режиме реального времени и полную прозрачность рабочих процессов. Рабочие задачи визуально представлены на доске Kanban, что позволяет участникам команды видеть состояние каждой задачи в любой момент времени.
- Understanding of the purpose of using Jira systems - платформа для управления проектами, задачами и отслеживания ошибок;
## level 3:  
- Understanding of primary SDLC models;
  - Жизненный цикл разработки ПО (System/Software Development Life Cycle, SDLC);
    - Исследование. Группа разработчиков собирает требования к проекту и включает их в документ «Спецификации требований к программному обеспечению» (SRS).
    - Дизайн. Команда анализирует все требования и выкатывает прототип системы.
    - Кодирование. Как только заинтересованные стороны проекта согласовывают прототип, начинается фаза написания кода.
    - Тестирование. Команда QA запускает каждый модуль через различные сценарии тестирования и интегрирует их в систему. Как только все компоненты на месте, они тестируют систему целиком.
    - Развертывание. Решение доставляется заказчику в полностью рабочем состоянии.
    - Обслуживание.
  - Каскадная модель (waterfall) - Это линейная и последовательная модель разработки программного обеспечения, в которой фазы проекта следуют одна за другойж
    - V-образная модель – это своего рода другая версия каскада, но в её основе лежит контроль качества каждой фазыж
    - Модель эволюционного прототипированияж
  - Итеративная и инкрементальная модель - решение разрабатывается небольшими частями через серию циклов
  - Спиральная модель - сочетает в себе функции каскадной, прототипной, итеративной и инкрементной моделей. Модель похожа на спираль с несколькими кругами.
- Applying principals of selected SDLC model in practice;
## level 4:  
- agile vs scrum/kanban; - Если фреймворк Scrum сразу определяет рамки процесса, то канбан-метод встраивается в любой существующий и позволяет начать с того, что есть сейчас, постепенно его улучшая.
- providing estimates of efforts required for implementing the tasks;

# 19. Browser. Events (required level 3)
## level 1:  
- DOM events;
   -https://learn.javascript.ru/introduction-browser-events
- Handling (add/remove event handlers);
  - https://learn.javascript.ru/introduction-browser-events#obrabotchiki-sobytiy
## level 2:   
- Basic types of DOM events;
  - mouse events ( MouseEvent ): mousedown, mouseup, click, dblclick, mousemove, mouseover, mousewheel, mouseout, contextmenu.
  - touch events ( TouchEvent ): touchstart, touchmove, touchend, touchcancel.
  - keyboard events ( KeyboardEvent ): keydown, keypress, keyup.
  - form events: focus, blur, change, submit.
## level 3:  
- Ways to prevent DOM event;
  - https://learn.javascript.ru/bubbling-and-capturing#prekraschenie-vsplytiya
  - stopPropagation() - препятствует продвижению события дальше, но на текущем элементе все обработчики будут вызваны.
  - event.stopImmediatePropagation() - Для того, чтобы полностью остановить обработку, существует метод 
## level 4:  
- Events propagation (bubbling/capturing);
  - https://learn.javascript.ru/bubbling-and-capturing
- Events delegation;
  - https://learn.javascript.ru/event-delegation


# 20. Cookie (required level 3)
## level 1:  
- -
## level 2:  
- -
## level 3:  
- [What is cookie;](https://learn.javascript.ru/cookie#chtenie-iz-document-cookie)
## level 4:  
- [Setting and getting of cookies;](https://learn.javascript.ru/cookie#chtenie-iz-document-cookie)
- Age of cookie;](https://learn.javascript.ru/cookie#expires-max-age) 


# 21. HTML. Semantic, Critical Rendering path, block/inline elements (required level 3)
## level 1:  
- Basic scheme for HTML document;
  - https://ru.hexlet.io/courses/layout-designer-basics/lessons/page-structure/theory_unit
- HTML symbols usage;
- Text formatting, paragraphs;
## level 2:  
- HTML links. Link target;
  - https://developer.mozilla.org/ru/docs/Web/HTML/Element/A
- HTML tables;
- Adding of scripts;
  - http://htmlbook.ru/html/script
- Basic html elements (block, input, nav, select, p, li, button, forms, etc.)
  - https://developer.mozilla.org/ru/docs/Web/HTML/Element/Input#notes
## level 3:  
- Difference between block and inline elements;
  - https://itchief.ru/html-and-css/display
- Types of inputs;
    - text: Однострочное текстовое поле. Переносы строк автоматически удаляются из входного значения.
    - button: Кнопка без предопределённого поведения.
    - checkbox: Флажок («чекбокс»). Следует использовать атрибут value для определения значения, которое будет отдано этим элементом. Используйте атрибут checked, чтобы указать, должен ли флажок быть выставлен. Можно также использовать атрибут indeterminate, чтобы указать, что флажок находится в неопределённом состоянии (на большинстве платформ при этом рисуется горизонтальная линия поперёк флажка).
    - date: HTML5 Элемент управления для ввода даты (год, месяц и день, без времени).
    - time: HTML5 Элемент управления для ввода значения времени без часового пояса.
    - number: HTML5 Элемент управления ввода числа(тип float).
    - month: HTML5 Элемент управления для ввода месяца и года без часового пояса.
    - email: HTML5 Поле для редактирования адреса электронной почты. Перед отправкой проверяется, что входное значение содержит либо пустую строку, либо один действительный адрес электронной почты. Соответствуют CSS псевдоклассам :valid and :invalid.
    - file: Элемент управления, который позволяет пользователю выбрать файл. Используйте атрибут accept, чтобы определить типы файлов, которые могут быть выбраны.
    - hidden: Элемент управления, которые не отображается, но чьё значение отправлено на сервер
    - password: Однострочное текстовое поле, чьё значение скрыто символом "звёздочка". Используйте атрибуты minlength и maxlength, чтобы указать минимальную и максимальную длину значения, которое может быть введено.
    - adio: Кнопка-переключатель, позволяет выбрать одно значение из множественного выбора.
    - range: HTML5Элемент управления для ввода числа, точное значение которого не имеет значения. Этот тип управления использует следующие значения по умолчанию, если соответствующие атрибуты не указаны:
    - reset: Кнопка сброса содержимого формы в состояние по умолчанию.
    - submit: Кнопка для отправления формы.
    - tel.
- Types of buttons;
    - button -The button is a clickable button
    - submit - submits form-data
    - reset	- resets the form-data to its initial values)
- Work with forms;
  - https://webref.ru/course/html-content/forms
## level 4:  
- Media (basic understanding what is it and for what);
- Critical Rendering path
  - построение DOM-дерева,
  - построение CSSOM-дерева,
  - запуск JavaScript,
  - создание Render-дерева,
  - генерация раскладки,
  - отрисовка.


# 22. CSS. Selector types, Selector weight, styles that are inherited (required level 3)
## level 1:  
- Frameworks layout technique;
- Selectors and their weight;
- Positioning;
- Margings vs paddings;
## level 2:  
- Fonts adding;
- Element visibility. Ways to hide element;
- Inline/block/block-inline elements, difference
## level 3:  
- Z-index;
- Types of position;
- Types of display;
## level 4:  
- Flexbox layout technique;
- Responsive design (concept understanding);
- CSS Box Model


# XX. Nam (required level x)
## level 1:  

## level 2:  

## level 3:  

## level 4:  

