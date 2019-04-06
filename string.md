# String
 
 - Используем `''` и ` `` `
    ```javascript
    const str = 'Abcde';
    
    const html = `
      <button>Click me</button>
      <p>${ str }<p>
    `;
    ```
 - [cahrAt](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt) 
   -- возвращает символ по индексу или `''` 
    ```javascript
    console.log(
      'Abcde'.length === 5,
      'Abcde'[0] === 'A',
      'Abcde'.charAt(20) === '', 
      'Abcde'[20] === undefined, 
    );
    
    // str[2] = '0'; // Ошибка, строку нельзя менять
    ```
 - [includes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes)
   -- `true`/`false` если **строка** содержит **подстроку**
 - [indexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf)
   -- индекс или `-1`, начиная с которого **подстрока** входит в **строку**
 - [lastIndexOf](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf)
   -- index или `-1` последнего вхождения (считается от начала) 
 - [startsWith](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith)
   -- `true`/`false` если **строка** начинается с **подстроки**
 - [endsWith](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith)
   -- `true`/`false` если **строка** заканчивается **подстрокой**
 - [localeCompare](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/localeCompare)
   - `-1` если **строка** стоит раньше **подстроки** в словаре
   - `1` если **строка** стоит в словаре позже **подстроки**
   - `0` если они равны
    ```javascript
    console.log(
      'Abcde'.includes('bc') === true,     // содержит ли вообще
      'Abcde'.includes('bc', 2) === false, // содержит ли начиная с 2 позиции
   
      'Abcde'.indexOf('bc') === 1,         // позиция первого вхождения
      'Abcde'.indexOf('bc', 2) === -1,     // позиция начиная синдекса 2
   
      'Abcde'.lastIndexOf('bc') === 1,     // позиция последнего вхождения
   
      'Abcde'.startsWith('Ab') === true,   // arg является началом
      'Abcde'.endsWith('de') === true,     // arg является окончанием
   
      'Abcde'.localeCompare('aaa') === 1,  // arg стоит в словаре раньше
    );
    ```
 - [slice](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice)
   -- взять часть строки
    ```javascript
    console.log(
      'Abcde'.slice(1, 3) === 'bc',   // 1 и 2 символы
      'Abcde'.slice() === 'Abcde',    // копия всей строки
      'Abcde'.slice(-3, -1) === 'cd', // 3 и 2 с конца
      'Abcde'.slice(-2) === 'de',     // последние 2 символа
    );
    ```
 - [replace](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
   -- заменяет первое вхождение подстроки на другую (или все для `RegExp` c флагом `g`)
    ```javascript
    console.log(
      'Abababab'.replace('ab', '12') === 'Ab12abab', // Поиск по строке
      'Abababab'.replace(/ab/i, '12') === '12ababab', // RegExp без учёта регистра
      'Abababab'.replace(/ab/g, '12') === 'Ab121212', // RegExp глобально
      'Abababab'.replace(/ab/ig, '12') === '12121212', // RegExp глобально без учёта регистра
    );
    ```
 - [toUpperCase](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase)
   -- перевести в верхний регистр
 - [toLowerCase](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase)
   -- перевести в нижний регистр
 - [trim](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim)
   -- убирает порбелы по краям
 - [trimStart](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimStart)
   -- убирает порбелы вначале (алиас `trimLeft`)
 - [trimEnd](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trimEnd)
   -- убирает порбелы вконце (алиас `trimRight`)
    ```javascript
    console.log(
      'Abcde'.toUpperCase() === 'ABCDE', 
      'Abcde'.toLowerCase() === 'abcde',   
      ' \t a\n '.trim() === 'a',
      ' \t a\n '.trimStart() === 'a\n ',
      ' \t a\n '.trimEnd() === ' \t a',
    );
    ```
 - [repeat](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/repeat)
   -- повторяет строку указанное число раз
 - [padStart](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padStart)
   -- дополняет строку до нужной длинны символами в начале
 - [padEnd](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/padEnd)
   -- дополняет строку до нужной длинны символами в конце
    ```javascript
    console.log(
      'az'.repeat(3) === 'azazaz',
      '4567'.padStart(10, '*') === '******4567',
      '4567'.padEnd(10, '*') === '4567******',
    );
    ```
