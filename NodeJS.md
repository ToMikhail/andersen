[be back](https://github.com/ToMikhail/andersen)
___

# 1. Node.js API (required level 3)   

Node.js — не отдельный язык программирования, а платформа для использования JavaScript на стороне сервера. Если говорить о языке, то как для фронденда, так и для бэкенда используется один и тот же JavaScript. Разница только в наборе API, которые используют фронтендеры и бэкендеры.

   ***level 1:*** 
   
   - ***http module***. Basic understanding of http module, it's  purpose and details;
   - ***timers api***. Basics of timers api;
   - difference between ***browser and node api***;
   
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
   
   - Basics of "process" and node js process module;
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


