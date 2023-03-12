[be back](https://github.com/ToMikhail/andersen)
___

# 1. Node.js API (required level 3)   

Node.js — не отдельный язык программирования, а платформа для использования JavaScript на стороне сервера. Если говорить о языке, то как для фронденда, так и для бэкенда используется один и тот же JavaScript. Разница только в наборе API, которые используют фронтендеры и бэкендеры.

   ***level 1:*** 
   
   - ***http module***. Basic understanding of http module, it's  purpose and details;
   ```
   const http = require('http)
   
   // create server
   const server = http.createServer((req, res) => {
   	console.log(req.url);
	
	res.write('<h1>Hello word from node JS</h1>')
	res.end()
   })
   
   //run server
   server.listen(3000, () => {
   	console.log('server is running')
   })
   ```
   
   - ***timers api***. Basics of timers api;
>Setting Node.js timer functions
setTimeout()
setInterval()
setImmediate()
>Clearing Node.js timer functions
clearTimeout()
clearInterval()
clearImmediate() - функция setImmediate() будет запущена после завершения всего исполняемого кода. Функция setImmediate() запускает код после завершения текущего цикла цикла обработки событий. setImmediate() похож на setTimeout() с задержкой 0 мс.
>Other Node.js timer functions
unref()
ref()
   - difference between ***browser and node api***;
   >В браузере большую часть времени вы взаимодействуете с DOM или другими API-интерфейсами веб-платформы, такими как файлы cookie. Конечно, в Node.js их нет. У вас нет документа, окна и всех других объектов, предоставляемых браузером.
   >А в браузере у нас нет всех хороших API-интерфейсов, которые Node.js предоставляет через свои модули, таких как функциональность доступа к файловой системе.
   >Еще одно большое отличие заключается в том, что в Node.js вы контролируете среду. Если вы не создаете приложение с открытым исходным кодом, которое любой может развернуть где угодно, вы знаете, на какой версии Node.js вы будете запускать приложение. По сравнению со средой браузера, где вы не можете позволить себе роскошь выбирать, какой браузер будут использовать ваши посетители, это очень удобно.
   >Это означает, что вы можете написать весь современный JavaScript ES2015+, который поддерживает ваша версия Node.js. Поскольку JavaScript развивается так быстро, а браузеры могут немного медленно обновляться, иногда в Интернете вы застреваете на старых версиях JavaScript/ECMAScript. Вы можете использовать Babel для преобразования вашего кода в ES5-совместимый перед его отправкой в d браузер, но в Node.js вам это не понадобится.
   >Еще одно отличие состоит в том, что Node.js поддерживает системы модулей CommonJS и ES (начиная с Node.js v12), в то время как в браузере мы начинаем видеть реализацию стандарта модулей ES. На практике это означает, что вы можете использовать как require(), так и импорт в Node.js, в то время как вы ограничены импортом в браузере.
   
   ***level 2:***
   
   - Basics of file system api, how to work with files;    
   >есть два типа методоы: Synс и async. Sync не рекомендуется использовать(не блокирует поток). 
   
  *  fs.mkdir(path.join(__dirname, 'folder-name'), err => {}) - для создания папки.
  *  fs.writeFile(path.join(__dirname, 'folder-name'), err => {}) - для создания файла. Каждый раз файл бедт перезаписываться
  *  fs.appendFile(path.join(__dirname, 'folder-name'), err => {}) - для ставки контента в файл
  * fs.writeFile(path.join(__diname, ''folder-name'', 'file-name.txt'), (err, data) => {}) - для чтения файлов. Данные приходят в буфере (часятим). Что бы полчить нормальный формат необходимо вторым прпметром указать кодировку 'utf-8', или трансформировать данные через метод Buffer.from(data).toString()
   
  ```
   fs.mkdir(path.join(__dirname, 'folder-name'), err => {
    if (err) throw new Error(err)
     console.log('папка создана')
     })
   ```
   
   
   - Understanding of Event Based approach, Events API   
   >При сиздании класса делаем extands EventEmmiter который под капотом имеет два метода on() и emmit(). 
   >Идея проста — объекты-эмиттеры отправляют именованные события, которые запускают уже зарегистрированных слушателей. Следовательно, объект-эмиттер имеет две ключевые характеристики:
  * Генерация событий name: Сигнал о том, что что-то произошло, называется генерацией события. Причиной этого состояния часто является изменение состояния излучающего объекта. 
  * Регистрация и отмена регистрации функций прослушивателя: это относится к привязке и отвязке функций обратного вызова с соответствующими им событиями.
  ```
  // Import the 'events' module
const events = require('events');

// Instantiate an EventEmitter object
const eventEmitter = new events.EventEmitter();

// Handler associated with the event
const connectHandler = function connected() {
	console.log('Connection established.');

	// Trigger the corresponding event
	eventEmitter.emit('data_received');
}

// Binds the event with handler
eventEmitter.on('connection', connectHandler);

// Binds the data received
eventEmitter.on(
	'data_received', function () {
		console.log('Data Transfer Successful.');
	});

// Trigger the connection event
eventEmitter.emit('connection');

console.log("Finish");
  ```
   
   ***level 3 (required):***
   
   - Basics of "process" and node js process module - Объект процесса предоставляет информацию о текущем процессе Node.js и управляет им. Объект процесса является экземпляром EventEmitter.;
	 * Событие 'beforeExit' - Событие генерируется, когда Node.js очищает свой цикл событий и не имеет дополнительной работы для планирования. Обычно процесс Node.js завершается, когда нет запланированной работы, но слушатель зарегистрирован на 'beforeExit' может выполнять асинхронные вызовы и тем самым вызывать продолжение процесса Node.js.
	 * Событие: 'disconnect' - Если процесс Node.js порождается с каналом IPC (см. Дочерний процесс а также Кластер документация), 'disconnect' событие будет сгенерировано, когда канал IPC будет закрыт.
	 * Событие: 'exit' - В 'exit' Событие генерируется, когда процесс Node.js собирается завершить работу в результате: 
	- В process.exit() явно вызываемый метод;
	- Цикл событий Node.js больше не требует дополнительной работы.


   - Basics of child process module, knowledge of creating/managing this processes;
   - Basics of Error and error handling for Node API;
   
   ***level 4:***
   
   - Basics of cluster module and it's practical usage;
   - Basics of Streams API, where to use, specification of Streams;


___

# 2. Database (required level 3)

## 2.1 Tables, relationships, keys, constraints(required level 3)

  ***level 1:***  
  
  ***level 2:***
  
  - Can give definitions "table", "field", "record"
  
  ***level 3 (required):***
  
  - Can define the concept of "constraint", give examples + what is used for each

  ***level 4:***
  
  - Understanding the relationships between tables;
  - Knows how to organize all kinds of relationships
___

## 2.2 Creating, modifying, removing database objects: databases, tables, columns, indexes (required level 4)

  ***level 1:***  
  
  ***level 2:***
  
  -  Knowledge of commands for the listed operations;
  
  ***level 3 (required):***
  
  - Knowledge of syntax + ability to solve problems for these operations

  ***level 4:***
  
  - Understanding indexes;
  - What the indexes are used for;
  - How indexes work
  
___

## 2.3 Data manipulation (insert, update, delete) (required level 4)

  ***level 1:***  
  
  ***level 2:***
  
  -  Knowledge of operator groups (DML, DCL, TCL, DDL)


  ***level 3 (required):***
  
  - Knowing what each operator is used for


  ***level 4:***
  
  - Knowledge of the syntax for operators;
  - Give examples of use (task)
  
  
___

## 2.4 Retrieving data (simple select statement) (required level 3)

  ***level 1:***  
  
  - What is a request;
  - How is it initialized


  ***level 2:***
  
  - Give an example in practice of how a request is made (with / without a condition)


  ***level 3 (required):***
  
  - Give an example of sampling with multiple conditions

  ***level 4:***
  
  - Knowledge of subqueries;
  - Give an example of a selection with a subquery


___

## 2.5 "Transactions" (required level 2)

  ***level 1:***  
  
  - What is a transaction;
  - Transaction concepts (ACID)


  ***level 2:***
  
  - Knowledge of the commands used for the transaction


  ***level 3 (required):***
  
  - GGive a practical example of a transaction


  ***level 4:***
  
  - Transaction isolation levels
___

## 2.6 CRUD concept (required level 4)

  ***level 1:***  
  
  -
  ***level 2:***
  
  -  
  ***level 3 (required):***
  
  - 

  ***level 4:***
  
  - значение CRUD. Соотношение операций акронима с SQL опреаторами


___


