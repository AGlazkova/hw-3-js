## retake-3-js

#### 1. Custom Array.prototype.filter
```js
function customFilter(array, filterFn, inplace = false) {
    if (inplace) {
        for (let i = array.length - 1; i >= 0; i--) {
            if (!filterFn(array[i], i, array)) {
                array.splice(i, 1);
            }
        }
        return array;
    } 
    else {
        const filteredArray = [];
        for (let i = 0; i < array.length; i++) {
            if (filterFn(array[i], i, array)) {
                filteredArray.push(array[i]);
            }
        }
        return filteredArray;
    }
}


const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];
const result = customFilter(words, (word) => word.length > 6);
console.log(result) 
```


#### 2. Ключи и свойства
```js
function solutionFn(object) { 
  const resultObj = {}; 
  for (let key in object) { 
    const type = typeof object[key]; 
    if (resultObj[type]) { 
      resultObj[type]++; 
    } else {
      resultObj[type] = 1; 
    }
  }
  return resultObj;
};

const initialObj = {
  a: 'some string 1',
    b: 42,
    c: { c1: 'some string 2' },
    d: [],
    e: 123,
};
const resultObj = solutionFn(initialObj);
console.log(resultObj) 
```


#### 3. Больше никаких шуток про 1 + '1' === '11'
```js
function sum(a, b) {
    const isNumLeft = typeof a === 'number'
    const isNumRight = typeof b === 'number'

    if (isNumLeft & isNumRight) {
        return a + b;
    } else if (!isNumRight & isNumLeft) {
        throw new Error("The right operand is not number");
    } else if (!isNumLeft & isNumRight) {
        throw new Error("The left operand is not number");
    } else { 
      throw new Error("Operands are not numbers"); 
    }
}


console.log(sum(1, 1))
```


#### 4. CVS на минималках
```js
function getMinimalCVS(array) {
  const history = [array.slice()] 
  return {
    head: () => array.slice(), 
    history: () => history.slice(), 
    push: (new_entry) => {
      array.push(new_entry); 
      history.push(array.slice());
    }, 
    pop: () => {
      const new_entry = array.pop();
      history.push(array.slice()); 
      return new_entry 
    }
  };
}


const cvs = getMinimalCVS(['a', 'b', 'c']);

console.log(cvs.head());    // ['a', 'b', 'c']
console.log(cvs.pop());     // 'c'

cvs.push('d');
cvs.push('e');

console.log(cvs.head());    // ['a', 'b', 'd', 'e']
console.log(cvs.history());
/**
 * [
 *   ['a', 'b', 'c'],
 *   ['a', 'b'],
 *   ['a', 'b', 'd'],
 *   ['a', 'b', 'd', 'e']
 * ]
 */
```


#### 6. Hit Or Run
```js
function hitOrRun(a, b) {
  let randomNumber = Math.floor(Math.random() * (b - a + 1)) + a; 
  if (randomNumber < 2) { 
    return "hit";
  }
  for (let divisor = 2; divisor <= Math.sqrt(randomNumber); divisor++) { 
    if (randomNumber % divisor === 0) {
      return "hit" + '\n' + randomNumber; 
    }
  }
  return "run" + '\n' + randomNumber;
}


console.log(hitOrRun(5, 16))
```
