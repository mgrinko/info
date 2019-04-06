# Array

## Создать массив

```javascript
console.log(
  ['a', 'b', 'c'], 
  new Array('a', 'b', 'c'),

  'abc'.split(''),   // ['a', 'b', 'c']
  Array.from('abc'), // ['a', 'b', 'c']

  
  Array.from({
    0: 'a',
    1: 'b',
    2: 'c',
    length: 3,
  }), // ['a', 'b', 'c']
  
  Array(3), // Массив с длинной но без элементов
  Array(3).fill(1) // [1, 1, 1]
);
```


## Полезные методы

 - [.join(str1)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
   -- **Cтрока** полученная вставкой `str1` между элементами
    ```javascript
    console.log(
      [1, 2, 3].join('--') // '1--2--3'
    )
    ```
 - [.includes(item, position)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/includes)
   -- `true`/`false` - если `item` есть в массиве (`===`), если искать начиная с `position`
    ```javascript
    console.log(
      ['11', '22', '33'].includes('11'), // true 
      ['11', '22', '33'].includes('1'), // false 
      ['11', '22', '33'].includes(11), // false (потому что проверяется ===)
      ['11', '22', '33'].includes('11', 1), // false (потому что ищем начиная с индекса 1)
    )
    ```
 - [.indexOf(item, position)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf)
   -- `-1` или номер **первой** ячейки в которой хранится `item`, если искать начиная с `position`
    ```javascript
    console.log(
      ['a', 'b', 'c', 'a'].indexOf('a'), // 0
      ['a', 'b', 'c', 'a'].indexOf('x'), // -1
      ['a', 'b', 'c', 'a'].indexOf('a', 1), // 3 (потому что ищем начиная с индекса 1)
    );
    ```
 - [.lastIndexOf(item, position)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf)
   -- `-1` или номер **последней** ячейки в которой хранится `item`, если искать **назад** от `position`
    ```javascript
    console.log(
      ['a', 'b', 'c', 'a'].lastIndexOf('a'), // 3
      ['a', 'b', 'c', 'a'].lastIndexOf('x'), // -1
      ['a', 'b', 'c', 'a'].lastIndexOf('a', 2), // 0
    );
    ```


## Мутирующие методы (изменяют исходный массив)

 - [.push(x1, x2, ...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/push)
   -- **Добавить** `x1`, `x2`, ... в `конец` массива
    ```javascript
    const numbers = [0, 1, 2, 3];
    const newLength = numbers.push(4, 5, 6);
    console.log(numbers); // [0, 1, 2, 3, 4, 5, 6];
    console.log(newLength); // 7 - новая длинна массива
    ```
 - [.pop()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/pop)
   -- **Удалить** `последний` элемент массива
    ```javascript
    const numbers = [0, 1, 2, 3];
    const deletedItem = numbers.pop();
    console.log(numbers); // [0, 1, 2];
    console.log(deletedItem); // 3 - удалённый элемент
    ```
 - [.unshift(x1, x2, ...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
   -- **Добавить** `x1`, `x2`, ... в `начало` массива
    ```javascript
    const numbers = [0, 1, 2, 3];
    const newLength = numbers.unshift(4, 5, 6);
    console.log(numbers); // [4, 5, 6, 0, 1, 2, 3];
    console.log(newLength); // 7 - новая длинна массива
    ```
 - [.shift()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/shift)
   -- **Удалить** `первый` элемент массива
    ```javascript
    const numbers = [0, 1, 2, 3];
    const deletedItem = numbers.shift();
    console.log(numbers); // [1, 2, 3];
    console.log(deletedItem); // 0 - удалённый элемент
    ```
 - [.splice(start, count, x1, x2, ...)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/splice)
   -- **Удалить** `count` элементов из массива начиная с позиции `start` и вставить `x1`, `x2`, ... на их место
    ```javascript
    const numbers = [0, 1, 2, 3, 4, 5, 6];
    const deletedItems = numbers.splice(2, 3, 'a', 'b');
    console.log(numbers); // [0, 1, 'a', 'b', 5, 6];
    console.log(deletedItems); // [2, 3, 4] - то что удалили
    ```
 - [.fill(value, start, end)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/fill)
   -- **Заполнить** массив значением `value` начиная с позиции `start` до `end` (не включая)
    ```javascript
    const numbers = [0, 1, 2, 3, 4, 5];
    const results = numbers.fill('x', 2, 4);
    console.log(numbers); // [0, '1, 'x', 'x, 4, 5];
    console.log(results === numbers); // true - ссылка на тот же массив, удобно для цепочки
    ```
 - [.reverse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reverse)
   -- **Поменять** порядок элементов в массиве на противоположный
    ```javascript
    const numbers = [0, 1, 2, 3, 4, 5];
    const results = numbers.reverse();
    console.log(numbers); // [5, 4, 3, 2, 1, 0]
    console.log(results === numbers); // true - ссылка на тот же массив, удобно для цепочки
    ```
 - [.sort()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
   -- **Отсортировать** массив в алфавитном порядке (сравнивая элементы как строки)
    ```javascript
    const numbers = [3, 12, 2, 11];
    const results = numbers.sort();
    console.log(numbers); // [11, 12, 2, 3] - сортировка по UTF8 кодам первых символов
    console.log(results === numbers); // true - ссылка на тот же массив, удобно для цепочки
    ```
 - [.sort(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort#Parameters)
   -- сортирует массив по результатам `callback` (число)
    ```javascript
    const numbers = [3, 12, 2, 11];
    numbers.sort((number1, number2) => number1 - number2);
    console.log(numbers); // [2, 3, 11, 12]
    
    const words = ['ёж', 'як', 'аист'];
    console.log(
      words.sort(), // ['аист', 'як', 'ёж'] - код 'ё' больше 'я'
      words.sort(
        (word1, word2) => word1.localeCompare(word2) 
      ), // ['аист', 'ёж', 'як'] - правильная сортировка
    );
    ```


## Немутирующие методы (создаётся новый массив, старый остаётся неизменным)

 - [.slice(start, end)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/slice)
   -- **Новый массив** c элементами старого начиная с позиции `start` до `end` (не включая)
    ```javascript
    const numbers = [0, 1, 2, 3, 4, 5];
    console.log(
      numbers.slice(), // [0, 1, 2, 3, 4, 5] - копия
      numbers.slice(2), // [2, 3, 4, 5]
      numbers.slice(-2), // [4, 5]
      numbers.slice(2, 4), // [2, 3]
      numbers.slice(1, -2), // [1, 2, 3]
    );    
    ``` 
 - [.concat(arr1, x1, x2, arr2, ...)]()
   -- **Новый массив** со всеми элемнтами старого + всё что в скобках (из массивов берутся их элементы)
    ```javascript
    const numbers = [0, 1];
    const letters = ['a', 'b'];
    const tens = [10, 20];
    console.log(
      numbers.concat(), // [0, 1] - копия
      [...numbers], // новый способ - Деструктуризация
      
      numbers.concat(2, 3), // [0, 1, 2, 3]
      [...numbers, 2, 3],
   
      numbers.concat(letters, tens), // [0, 1, 'a', 'b', 10, 20]
      [...numbers, ...letters, ...tens],
   
      numbers.concat(2, letters, 3), // [0, 1, 2, 'a', 'b', 3]
      [...numbers, 2, ...letters, 3],
    );
    ```


## Перебираем 

 - [.forEach(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
   -- запускает `callback` для каждого элемента массива, возвращает `undefined`
    ```javascript
    const callback = function (element, index, arr) {
      console.log(element, index, arr);
    };
    const result = ['a', 'b', 'c'].forEach(callback);
       // 'a' 0 ['a', 'b', 'c']
       // 'b' 1 ['a', 'b', 'c']
       // 'c' 2 ['a', 'b', 'c']
    console.log(result); // undefined
    ```
 - [.map(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
   -- запускает `callback` для каждого элемента массива и складывает результаты в **новый массив**
    ```javascript
    const callback = (element, index, arr) => (element + index);
    console.log(
      [10, 20, 30].map(callback), // [10, 21, 32]
      [10, 20, 30].map(el => el + 5), // [15, 25, 35]
    );
    ```
 - [.filter(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
   -- запускает `callback` для каждого элемента массива и складывает в **новый массив** только те элементы старого,
   для которых функция вернула `true` (или эквивалент) 
    ```javascript
    const callback = (el, i, arr) => el > arr.length;
    console.log(
      [1, 4, 7].filter(callback), // [4, 7]
      [1, 4, 7].filter(el => (el % 2 === 0)), // [4]
    );
    ```
 - [.find(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/find)
   -- возвращает **первый элемент** массива, для которого функция возвращает `true` (или эквивалент)
 - [.findIndex(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/findIndex)
   -- возвращает `-1` или **позицию первого элемента** массива, для которого функция возвращает `true` (или эквивалент)
    ```javascript
    const callback = (el, i, arr) => el > arr.length;
    console.log(
      [1, 4, 7].find(callback), // 4
      [1, 4, 7].findIndex(callback), // 1

      [1, 4, 7].find(el => el > 10), // undefined
      [1, 4, 7].findIndex(el => el > 10), // -1
    );
    ```
 - [.every(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
   -- возвращает `true`/`false` если для каждого элемента в массиве функция вернёт `true` (или аналог)
 - [.some(callback)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/some)
   -- возвращает `true`/`false` если хотябы для 1 элемента в массиве функция вернёт `true` (или аналог)
    ```javascript
    const callback = (el, i, arr) => el > arr.length;
    console.log(
      [1, 4, 7].every(callback), // false
      [1, 4, 7].some(callback), // true
   
      [1, 4, 7].every(el => el > 0), // true
      [1, 4, 7].some(el => el > 0), // true
   
      [1, 4, 7].every(el => el > 10), // false
      [1, 4, 7].some(el => el > 10), // false
   
      [].every(el => el > 10), // true
      [].some(el => el > 10), // false
    );
    ```
 - [.reduce(callback, startValue)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
   -- запускает `callback` для каждого элемента массива и передаёт результат в качестве первого параметра
   для следующего запуска `callback`. Результат последнего запуска `callback` становится результатом `reduce`
