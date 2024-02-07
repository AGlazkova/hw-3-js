## retake-3-js

#### 1. Анаграмма
```js
 function anagram(srt1, str2) {
  const srt1Prepared = srt1.replace(/[^\w\s]|_/g, "").toLowerCase().split('').sort().join('');
  const srt2Prepared = str2.replace(/[^\w\s]|_/g, "").toLowerCase().split('').sort().join('');
  
  return srt1Prepared === srt2Prepared;
}


console.log(anagram('finder', 'Friend')); // true
console.log(anagram('hello', 'bye')); // false

```


#### 3. Палиндром
```js
function isPalindrome(str){
  let start = 0;
  let end = str.length-1;
  while(start < end){
    if(str[start].toLowerCase() !== str[end].toLowerCase()) return false;
    start++;
    end--;
  }
  return true;
}


```


#### 6. FizzBuzz
```js
function fizzBuzz(n) {
  for (let i = 1; i<= n; i++){
   if (i % 3 === 0 && i % 5 === 0) {
     console.log('fizzbuzz')     
      } else if (i % 3 === 0) {
        console.log('fizz')
      } 
       else if (i % 5 === 0) {
        console.log('buzz')
      } else {
       console.log(i)
      }
    }
  }


fizzBuzz(15);
```


#### 8. Симметрическая разность множеств
```js
function symmetricDifference(arr1, arr2) {
  const set1 = new Set(arr1);
  const set2 = new Set(arr2);
  const result = [];

  for (const num of arr1) {
    if (!set2.has(num)) {
      result.push(num);
    }
  }

  for (const num of arr2) {
    if (!set1.has(num)) {
      result.push(num);
    }
  }

  return result;
}


symmetricDifference([1, 5, 4, 2], [8, 91, 4, 1, 3]); // [5, 2, 8, 91, 3]
symmetricDifference([1, 5, 4, 2], [7, 12]); // [1, 5, 4, 2, 7, 12]
symmetricDifference([1, 5, 4, 2], [4, 1, 2, 5]); // []
```


#### 7. Уникальные числа
```js
const a = [1, 2, 3, 4, 3, 5, 7, 3, 2];
    
const arr = a.filter(function(item) {
  return a.lastIndexOf(item) == a.indexOf(item);
});

console.log(arr);

```
