[be back](https://github.com/ToMikhail/andersen)

# 18. Work with backend (required level 4)
**level 1:**
- [what is https;](https://developer.mozilla.org/ru/docs/Glossary/https)
- [what is status codes;](https://developer.mozilla.org/ru/docs/Web/HTTP/Status)
- [what is AJAX;](https://developer.mozilla.org/ru/docs/Web/Guide/AJAX)
- [what is JSON;](https://habr.com/ru/post/554274/)
  - (https://tproger.ru/articles/chto-takoe-json-vvedenie/)
**level 2:**  
- [Basic usage of XHR, how to make simple request and handle answer) response code groups](https://learn.javascript.ru/xmlhttprequest) 
  - (https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest)
  - [video.Minin.serverRequests](https://www.youtube.com/watch?v=eKCD9djJQKc)
- [Basic usage of fetch() (how to make simple request and handle answer);](https://developer.mozilla.org/ru/docs/Web/API/Fetch_API/Using_Fetch)
  - (https://learn.javascript.ru/fetch)
  - [fetch(video)](https://www.youtube.com/watch?v=eKCD9djJQKc)
**level 3:**
- CRUD HTTP methods;(https://proglib.io/p/chto-takoe-api-i-crud-prostymi-slovami)
- [What is REST?](https://medium.com/@andr.ivas12/rest-%D0%BF%D1%80%D0%BE%D1%81%D1%82%D1%8B%D0%BC-%D1%8F%D0%B7%D1%8B%D0%BA%D0%BE%D0%BC-90a0bca0bc78)
  - https://habr.com/ru/post/38730/
- CORS what is it -  Cross-Origin Resource Sharing («совместное использование ресурсов между разными источниками») -  механизм, использующий дополнительные HTTP-заголовки, чтобы дать возможность агенту пользователя получать разрешения на доступ к выбранным ресурсам с сервера на источнике (домене), отличном от того, что сайт использует в данный момент. Говорят, что агент пользователя делает запрос с другого источника (cross-origin HTTP request), если источник текущего документа отличается от запрашиваемого ресурса доменом, протоколом или портом.
- why do we need CORS 
  - (https://developer.mozilla.org/ru/docs/Web/HTTP/CORS)
  - (https://learn.javascript.ru/fetch-crossorigin#zachem-nuzhen-cors-ekskurs-v-istoriyu)
- Difference between PUT, PATCH, POST;(https://proglib.io/p/chto-takoe-api-i-crud-prostymi-slovami)
**level 4:**  
- What is CORS and why we need it;(https://habr.com/ru/company/macloud/blog/553826/)
- Work with json responce;(https://developer.mozilla.org/en-US/docs/Web/API/Response/json)
- Set headers in request;(https://developer.mozilla.org/ru/docs/Web/API/XMLHttpRequest/setRequestHeader)
- How to get around CORS;() - https://developer.mozilla.org/ru/docs/Web/HTTP/Headers/Access-Control-Allow-Origin

# 19. Development methodologies (agile and beyond) (required level 2)
**level 1:** 
- Why do we need metodology in our team;
- definition of agile;
**level 2:**  
- Definition of scrum and kanban. Base concept;  
  - SCRUM -  это набор правил для организации гибкого рабочего процесса, который заключается в командном подходе, работе итерациями, фокусировке на цели каждой итерации и нестандартном распределении обязанностей внутри коллектива.
  - Kanban — Методика предполагает обсуждение производительности в режиме реального времени и полную прозрачность рабочих процессов. Рабочие задачи визуально представлены на доске Kanban, что позволяет участникам команды видеть состояние каждой задачи в любой момент времени.
- Understanding of the purpose of using Jira systems - платформа для управления проектами, задачами и отслеживания ошибок;
**level 3:**  
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
**level 4:**  
- agile vs scrum/kanban; - Если фреймворк Scrum сразу определяет рамки процесса, то канбан-метод встраивается в любой существующий и позволяет начать с того, что есть сейчас, постепенно его улучшая.
- providing estimates of efforts required for implementing the tasks;

# 20. Browser. Events (required level 3)
**evel 1:**  
- DOM events;
   -https://learn.javascript.ru/introduction-browser-events
- Handling (add/remove event handlers);
  - https://learn.javascript.ru/introduction-browser-events#obrabotchiki-sobytiy
**level 2:**  
- Basic types of DOM events;
  - mouse events ( MouseEvent ): mousedown, mouseup, click, dblclick, mousemove, mouseover, mousewheel, mouseout, contextmenu.
  - touch events ( TouchEvent ): touchstart, touchmove, touchend, touchcancel.
  - keyboard events ( KeyboardEvent ): keydown, keypress, keyup.
  - form events: focus, blur, change, submit.
**level 3:**  
- Ways to prevent DOM event;
  - https://learn.javascript.ru/bubbling-and-capturing#prekraschenie-vsplytiya
  - stopPropagation() - препятствует продвижению события дальше, но на текущем элементе все обработчики будут вызваны.
  - event.stopImmediatePropagation() - Для того, чтобы полностью остановить обработку, существует метод 
**level 4:**  
- Events propagation (bubbling/capturing);
  - https://learn.javascript.ru/bubbling-and-capturing
- Events delegation;
  - https://learn.javascript.ru/event-delegation


# 21. Cookie (required level 3)
**level 1:**  
- -
**level 2:**  
- -
**level 3:**  
- [What is cookie;](https://learn.javascript.ru/cookie#chtenie-iz-document-cookie);- Куки – это небольшие строки данных, которые хранятся непосредственно в браузере. Они являются частью HTTP-протокола.   
Куки обычно устанавливаются веб-сервером при помощи заголовка Set-Cookie. Затем браузер будет автоматически добавлять их в (почти) каждый запрос на тот же домен при помощи заголовка Cookie.
Один из наиболее частых случаев использования куки – это аутентификация:      
      1. При входе на сайт сервер отсылает в ответ HTTP-заголовок Set-Cookie для того, чтобы установить куки со специальным уникальным идентификатором сессии («session identifier»).   
      2. Во время следующего запроса к этому же домену браузер посылает на сервер HTTP-заголовок Cookie.   
      3. Таким образом, сервер понимает, кто сделал запрос.   
 
**level 4:**  
- [Setting and getting of cookies;](https://learn.javascript.ru/cookie#chtenie-iz-document-cookie)
- Age of cookie;](https://learn.javascript.ru/cookie#expires-max-age) 


# 22. HTML. Semantic, Critical Rendering path, block/inline elements (required level 3)
**level 1:**  
- Basic scheme for HTML document;
  - https://ru.hexlet.io/courses/layout-designer-basics/lessons/page-structure/theory_unit
- HTML symbols usage;
- Text formatting, paragraphs;
**level 2:**  
- HTML links. Link target;
  - https://developer.mozilla.org/ru/docs/Web/HTML/Element/A
- HTML tables;
- Adding of scripts;
  - http://htmlbook.ru/html/script
- Basic html elements (block, input, nav, select, p, li, button, forms, etc.)
  - https://developer.mozilla.org/ru/docs/Web/HTML/Element/Input#notes
**level 3:**  
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
**level 4:**  
- Media (basic understanding what is it and for what);
- Critical Rendering path - https://habr.com/ru/post/320430/
  - построение DOM-дерева,
  - построение CSSOM-дерева,
  - запуск JavaScript,
  - создание Render-дерева,
  - генерация раскладки,
  - отрисовка.


# 23. CSS. Selector types, Selector weight, styles that are inherited (required level 3)
**level 1:**  
- Frameworks layout technique; - https://jazzteam.ru/technical-articles/overview-of-approaches-and-css-frameworks-for-adaptive-web-page-layout/
  - Фиксированная верстка (Fixed Layout)
  - Резиновая верстка (Elastic layout)
  - Адаптивная верстка (Adaptive Layout) -  с использованием медиа-запросов (@media)
  - Отзывчивая верстка (Responsive Layout)
- Selectors and their weight; - https://habr.com/ru/post/137588/
- Positioning - https://itchief.ru/html-and-css/positioning-elements#:~:text=CSS%20%D1%81%D0%B2%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%BE%20position%20%E2%80%94%20%D1%8D%D1%82%D0%BE%20%D0%BE%D0%B4%D0%BD%D0%BE,%D0%B4%D1%80%D1%83%D0%B3%D0%B8%D1%85%20%D1%8D%D0%BB%D0%B5%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2%20%D0%BD%D0%B0%20%D0%B2%D0%B5%D0%B1%2D%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B5.
   - static (статичное позиционирование);
   - relative (относительное);
   - absolute (абсолютное);
   - fixed (фиксированное);
   - sticky (липкое).
- Margings vs paddings;
**level 2:**  
- Fonts adding; - https://developer.mozilla.org/ru/docs/Web/CSS/@font-face
- Element visibility. Ways to hide element; - https://habr.com/ru/company/ruvds/blog/485640/
- Inline/block/block-inline elements, difference
**level 3:**  
- Z-index; - https://developer.mozilla.org/ru/docs/Web/CSS/z-index#:~:text=CSS%2D%D1%81%D0%B2%D0%BE%D0%B9%D1%81%D1%82%D0%B2%D0%BE%20z%2Dindex%20%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D1%8F%D0%B5%D1%82,%D1%8D%D0%BB%D0%B5%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2%20%D1%81%20%D0%BC%D0%B5%D0%BD%D1%8C%D1%88%D0%B8%D0%BC%20z%2Dindex.
- Types of position;
   - static (статичное позиционирование);
   - relative (относительное);
   - absolute (абсолютное);
   - fixed (фиксированное);
   - sticky (липкое).
- Types of display;- https://learn.javascript.ru/display
**level 4:**  
- Flexbox layout technique; - https://developer.mozilla.org/ru/docs/Web/CSS/CSS_Flexible_Box_Layout/Basic_Concepts_of_Flexbox
- Responsive design (concept understanding);
- CSS Box Model - https://developer.mozilla.org/ru/docs/Learn/CSS/CSS_layout/Flexbox
