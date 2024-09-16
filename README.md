Date : 16-sep-2024					    			         MicrocosmWork

    Documentation 

1. **Loops of NodeJS and Javascript**  
     
   **1.1 for loop**   
   	For loop in javascript as well as Nodejs this loop is used when we already know the iteration of iterator. (Number of repetition). Repeat the loop until the condition is true,  
   This loop take 3 arguments   
     
1. Initialization,  
2. condition,  
3. Increment or decrement.

   **Execution of for Loop**

   `1. Initialization (set loop variable)`

   `2. Check condition (if true, move to step 3)`

   `3. Execute code block`

   `4. Increment loop variable`

   `5. Repeat from step 2 if condition is true, else exit loop`

   

   

   `Code:-`

   `for (let i = 0; i < 5; i++) {`

     `console.log(i);`

   `}`

   

	

	**1.2 While loop**  
	While loop in javascript as well as Nodejs this loop is used when we don’t know the Number of repetition. Repeat the loop until the condition is true, take only 1 args.   
(it doesn’t execute if the starting condition of false)

1. Condition  
2. Execute the block of loop then increment the iterator   
3. Check if condition is still true then repeat again

   **Execution of for Loop**

    **`1. Check condition (if true, move to step 2)`**

   **`2. Execute code block`**

   **`3. Repeat from step 1 if condition is true, else exit loop`**

   **`Code:`**

   **`let i = 0;`**

   **`while (i < 5) {`**

     **`console.log(i);`**

     **`i++;`**

   **`}`**

   

	**1.3 do while loop**  
		This is similar to while loop but there is a difference while loop doesn't execute a single time if the Initialization (condition) is false, but in do while the loop body will execute 1 time even if the Initialization condition is false/wrong

`1. Execute code block`  
`2. Check condition (if true, move to step 1)`  
`3. Repeat if condition is true, else exit loop`

`code:`  
	`let i = 0;`  
`do {`  
  `console.log(i);`  
  `i++;`  
`} while (i < 5);`

**1.4 for…in loop**  
     Loop over the enumerable properties (those properties which can be iterated over the object).   
The      1\. Get key ( iterator)  
     2\. Execute block  
     3\. Move to next key  
     4\. Repeat from step 1 for remaining keys	  
	This loop run until the last key of object  
	Use: use for iterating over the object properties and Array indices.  
	**Execution of Loop**  
1\. Get the first property/key from the object   
2\. Execute code block   
3\. Move to next property/key   
4\. Repeat from step 1 for remaining properties  
	  
	

Code:  
const obj \= { a: 1, b: 2, c: 3 };  
for (let key in obj) {  
  console.log(key, obj\[key\]);  
}

**1.5 for…of loop**	  
	Loops over the values of an iterable (array, string, etc.).  
		For iterating over iterable objects (arrays, strings)  
***Mainly the difference between for in and for of loop is:***  
***For in loop iterate over the indices and properties.***  
***For of loop iterate over the value of iterable (array,string) which have   indices***   
	**Execution of loop**  
		1\. Get value  
2\. Execute block  
3\. Move to next value  
4\. Repeat from step 1 for remaining values

Code:   
const arr \= \[10, 20, 30\];  
for (let value of arr) {  
  console.log(value);  
}

**1.6 forEach loop**  
The `forEach` loop is a method available on arrays in JavaScript, and it provides a way to  execute a provided function once for each array element. It is a useful tool for performing operations on all elements of an array.  
**CB**: It takes a callback function as an argument, which is executed for each element of the array. The callback function can accept up to three arguments:

* The current element (`element`) →  The current element being processed.(value)  
* The index of the current element (`index`) → (optional): The index of the current element.  
* The array itself (`array`) → (optional): The array that `forEach` is being called upon.  
* Unlike `map` or `filter`, `forEach` does not return a new array. It is intended for side effects, not transformations.

  Code: 

  const arr \= \[1, 2, 3\];

  arr.forEach((element, index) \=\> {

    console.log(index, element);

  });


  

  **1.7 HighOrder Functions**

  	**1\. Map()**

   Map is the HighOrder method in javaScript.Map() is similar to forEach  	loop but there is some difference. Map returns the new Array unlike forEach.

  The `map` method creates a new array with the results of calling a provided function on every element in the calling array.


  Map is highOrder Function because it take the CB as arguments

  And it take several Arguments :

  		`element`: The current element being processed.(value) 

  `index` (optional): The index of the current element.

  `array` (optional): The array on which `map` was called.

			  
**Execution Flow**

1. `map` iterates over each element in the array.  
2. It applies the callback function to each element.  
3. It collects the return values from the callback function into a new array.  
4. The original array remains unchanged.

 **Mainly Map()  useCase is to Transforming the each element of an array into new value** 

**Code:**

const arr \= \[1, 2, 3\];

const doubled \= arr.map(x \=\> x \* 2);

console.log(doubled); // \[2, 4, 6\]

**1.8 Filter()**

The `filter` method creates a new array with all elements that pass the test implemented by the provided function.

Filter is HO function because it take the CB as arguments and it takes several arguments:

1. `element`: The current element being processed.(value)   
2. `index` (optional): The index of the current element.  
3. `array` (optional): The array on which `map` was called.

	**Execution Flow** 

1. `filter` iterates over each element in the array.  
   2. It applies the callback function to each element.  
      3. It includes elements that pass the test (callback returns `true`) in the new array.  
         4. The original array remains unchanged.  
2.  Use `filter` when you need to select a subset of elements from an array based on a condition.(for example we can create an union, set, intersection) or an Array using filters we can easily Neglect the unrequired or duplicate element value.

   

   Code: 

   const arr \= \[1, 2, 3, 4, 5\];

   const even \= arr.filter(x \=\> x % 2 \=== 0);

   console.log(even); // \[2, 4\]

   

	

**1.9 Reduce()**

The `reduce` method executes a reducer function (that you provide) on each 	element of the array, resulting in a single output value.

Filter is HO function because it take the CB as arguments and it takes several arguments:

1. `accumulator`: Accumulates the results. It’s the accumulated value returned from the last execution of the callback, or `initialValue` if provided.  
2. `element`: The current element being processed.  
3. `index` (optional): The index of the current element.  
4. `array` (optional): The array on which `reduce` was called.

   #### **Execution Flow**

1. `reduce` iterates over each element in the array.  
2. It applies the callback function, using the accumulator and current element to compute a new accumulator value.  
3. After processing all elements, `reduce` returns the final accumulator value.

   

   Code: 

   const arr \= \[1, 2, 3\];

   const sum \= arr.reduce((accumulator, currentValue) \=\> accumulator \+ currentValue, 0);

   console.log(sum); // 6

   

   

 


   	

   			**Promises**

**Promises:** JavaScript Promises are a key feature for handling asynchronous operations. They provide a way to execute code asynchronously and handle the result when it's available, or catch errors if something goes wrong.

**A Promise is an object representing the eventual completion or failure of an asynchronous operation.**

Promises has 3 status:

	1.Pending 

	2.Rejected

	3.Fulfilled

1.Pending state: the is the state where the promises are waiting to get rejected and resolve the Promises

This is an initialization of an Promises:

Then pending state when the promises is created and the work is onGoing 

Create Promises:

const promise \= new Promise((resolve, reject) \=\> {  
// promise block where u want to perform the operation which u want  
});

The Promise is ByDefault Async in nature.  
Not need to use Async/await while dealing with  promises

2\. Rejected state  
	In this state if a promise is rejected this state will occur, A JavaScript Promise gets rejected when the asynchronous operation it represents fails or encounters an error.

3\. Fulfilled state:  
	In this state if a promise completes the block of Promises without any Error this means promise is fulfilled state.

**Methods of Promise:**

1. .then()--\> this method execute immediately after the promise get response Either Reject or resolve  then() method takes CB and execute the CB  
2. .catch()--\> catch method is use to handle the sudden failure of promise or when the project is rejected   
3. finally()--\> finally method will execute fareless even if the promise reject or resolve it will run.  
     
   

**STATIC Method:**

#### **1\. `Promise.all(iterable)`**

* **Description:** Takes an iterable of promises (e.g., an array) and returns a single Promise that resolves when all the promises in the iterable have resolved. If any of the promises are rejected, the returned promise is rejected with the reason of the first rejected promise.  
  const promise1 \= Promise.resolve('Value 1');  
  const promise2 \= Promise.resolve('Value 2');  
  Promise.all(\[promise1, promise2\])  
    .then(results \=\> {  
      console.log(results); // \["Value 1", "Value 2"\]  
    })  
    .catch(error \=\> {  
      console.error('One of the promises failed:', error);  
    });  
    
    
  


  #### **2\. `Promise.allSettled(iterable)`**

* **Description:** Takes an iterable of promises and returns a single Promise that resolves after all of the given promises have either resolved or rejected. The returned promise resolves with an array of objects describing the outcome of each promise.  
* Means it will return the array of promises with all data of promise which is available in args array.  
  const promise1 \= Promise.resolve('Value 1');  
  const promise2 \= Promise.reject('Error');  
  Promise.allSettled(\[promise1, promise2\])  
    .then(results \=\> {  
      console.log(results);          // \[{ status: 'fulfilled', value: 'Value 1' }, { status: 'rejected', reason: 'Error' }\]  
    });

  #### **3\. `Promise.any(iterable)`**

* **Description:** Takes an iterable of promises and returns a single Promise that resolves as soon as one of the promises in the iterable resolves. If no promises resolve (i.e., all are rejected), the returned promise is rejected with an `AggregateError`, a subclass of `Error` that groups together individual errors.  
* `AggregateError→ An AggregateError is a special kind of error in JavaScript that represents multiple errors combined into a single error object.`  
  const promise1 \= Promise.reject('Error 1');  
  const promise2 \= Promise.resolve('Value 2');  
  Promise.any(\[promise1, promise2\])  
    .then(result \=\> {  
      console.log(result); // "Value 2"  
    })  
    .catch(error \=\> {  
      console.error('All promises were rejected:', error);  });

  #### 

  #### **4\. `Promise.race(iterable)`**

* **Description:** Takes an iterable of promises and returns a single Promise that resolves or rejects as soon as one of the promises in the iterable resolves or rejects. The returned promise adopts the state of the first settled promise.  
  const promise1 \= new Promise((resolve) \=\> setTimeout(resolve, 500, 'Value 1'));  
  const promise2 \= new Promise((resolve) \=\> setTimeout(resolve, 100, 'Value 2'));  
  Promise.race(\[promise1, promise2\])  
    .then(result \=\> {  
      console.log(result); // "Value 2" (since it resolves first)  
    });

  **Difference between promise.all() and promise.race()**

  #### **1\. Handling Resolved Promises:**

  **`Promise.any()`**:

  * Resolves as soon as **any one promise** resolves.  
  * If all promises are rejected, it rejects with an `AggregateError`.  
  * It ignores rejected promises unless all the promises are rejected.

            **`Promise.race()`**:

* Resolves or rejects as soon as the **first promise** settles, meaning it can resolve or reject based on which promise completes first.  
* It does not wait for the first resolved promise if an earlier promise rejects; it immediately resolves or rejects based on the first settled promise.

#### **2\. Rejection Handling:**

* **`Promise.any()`**:  
  * It **ignores** any rejected promises as long as at least one promise resolves.  
  * If **all promises are rejected**, it throws an `AggregateError`, containing all the rejection reasons.  
  * **Major Benefit:** It only cares about finding a resolved promise; it doesn’t fail if there are rejections, unless all reject.

| Feature | `Promise.any()` | `Promise.race()` |
| ----- | ----- | ----- |
| **Resolves** | When **any one** promise resolves. Ignores rejected ones (unless all reject). | When **the first** promise (resolved or rejected) settles. |
| **Rejects** | When **all promises are rejected** with an `AggregateError`. | When **the first** promise to settle rejects. |
| **Use Case** | Use when you're interested in at least one successful result, and you don't care about failed ones. | Use when you need the result of the first promise to settle, whether resolved or rejected. |

**Arrays**

**List of all array methods.**

**Iterator methods(CB & loops):-**

1.f**orEach(CB)-\>** it will execute the cb for each element of an iterator

		Code: array.forEach((element) \=\> { console.log(element); });

2\. **Map(cb)-\>** similar to forEach() but it will return the new Array 

Code: const newArray \= array.map((element) \=\> element \* 2);

3\. **filter(cb)-\>** filter method is a HO function which filters out the element into a new array based on a given condition.

Code: const filteredArray \= array.filter((element) \=\> element \> 10);

4\.**reduce(cb,initialValue)-\>** it will return the single variable output. Executes a reducer function (accumulator) on each element of the array.

Code: const sum \= array.reduce((acc, curr) \=\> acc \+ curr, 0);

5\.**reduceRight(cb,initial Value)-\>** similar to reduce() but it process the array for right to left (default precedence is left to right)

Code: const sum \= array.reduceRight((acc, curr) \=\> acc \+ curr, 0);

6\. **some(cb)-\>** check if at least one element pass the test implemented by provided function

Code: const hasLargeNumber \= array.some((element) \=\> element \> 10);

7\.**every(cb)-\>** similar to some but in every it work need to every Element should pass the test

Code: const allAboveZero \= array.every((element) \=\> element \> 0);

8\.**find(cb)-\>** return the value which is satisfied by first element

Code: const foundElement \= array.find((element) \=\> element \> 10);

9\.**findIndex(cb)-\>** return the index which is satisfied by first element

Code: const foundElement \= array.findIndex((element) \=\> element \> 10);

10\. **flatMap(cb)-\>** First maps each element using a mapping function, then flattens the result into a new array.

It is combination of map and flat, 1 it will mapping the array using map() and them flat () method use for flat the nested array

This method are especially use for handling the data which came from the API

Code: 

const apiResponse \= \[

  { userId: 1, posts: \["Post1", "Post2"\] },

  { userId: 2, posts: \["Post3", "Post4"\] }

\];

// Extract all posts from users and flatten into a single array

const allPosts \= apiResponse.flatMap(user \=\> user.posts);

console.log(allPosts);// Output: \["Post1", "Post2", "Post3", "Post4"\]

11**.push()-\>** entry the new element at the end of an array;

Code:

arr=\[1,2,4,4,5\]

arr.push(10)  \-\> \[1,2,4,4,5,10\]

12\. **pop()-**\> return out the last element of an array.

Code:

arr=\[1,2,4,4,5\]

arr.pop()  \-\> \[1,2,4,4\]

13\. **shift()-\>** enter the element at the first position of an array

Code:

arr=\[1,2,4,4,5\]

arr.shift(10)  \-\> \[10,1,2,4,4\]

14\.**unshift()-\>** similar to pop return out the first element of an array

Code:

arr=\[1,2,4,4,5\]

arr.unshift()  \-\> \[2,4,4\]

15 .**splice(start,deleteCount,...newelem)-**\> Changes the contents of an array by removing or replacing existing elements and/or adding new elements.

Code:

array.splice(2, 1, 'newElement');

16\.**reverse()-\>**  reverse an array 

Code:

array.reverse();

17\.**sort()-\>** sort the array in ascending as well as decreasing ( default ascending). Update an existing array

Code:

array.sort((a, b) \=\> a \- b); // Ascending order

18\.**fill(value,start,end)-\>** Fills all elements in an array from a start index to an end index with a static value.

Code:

array.fill(0, 1, 3);

19**.copyWithin(target,start,end)-\>**Shallow copies part of an array to another location in the same array without changing its length.

Code:

array.copyWithin(0, 3, 5);

20\.**concat()-\>** marge 2 or more array & return an new array

Code:  
const newArray \= array.concat(\[4, 5, 6\]);

21\. **slice(start,end)-\>**  Returns a shallow copy of a portion of an array into a new array object.	

	Code:

	const slicedArray \= array.slice(1, 3);

22\.**includes(element)-\>** check the given value is exist or not

Code:

const hasElement \= array.includes(3);

23**.indexOf(element)-\>** return the first index where given element exist else return \-1 if not

		Code:  
		const index \= array.indexOf(3);

24\. **lastIndexOf(element)-\>** Returns the last index at which a given element can be found, or \-1 if it is not present.

Code:

const lastIndex \= array.lastIndexOf(3);

25\. **Join()-\>**  join the array and return it into string

		Code:

const string \= array.join('-');

26\.**toString()-\> return the which is representing of an array**

Code:  
	const str \= array.toString();

27\.**flat(depth)-\>**  Flattens an array up to a specified depth and returns a new array.

Code:

const flatArray \= array.flat(1);

**Some methods which iterate over the Objects**

	**keys()-\>** return an new array which contains all the key of object

			Code:

const iterator \= array.keys();

	**values()-\>**  similar to keys() it will return the new array of an value

			Code:

const iterator \= array.values();

**entries()-\>** Returns a new Array Iterator object that contains key/value pairs for each         

          index in the array.

Code:	

const iterator \= array.entries();

**`Array.from(arrayLike, mapFn, thisArg)`**: Creates a new array from an array-like or iterable object.

Code:	

const newArray \= Array.from('hello'); 

o/p-\> \['h', 'e', 'l', 'l', 'o'\]

**`Array.of(...elements)`**: Creates a new array instance from a variable number of elements.

Code:	

const newArray \= Array.of(1, 2, 3);

**`isArray(value)`**: Determines if a value is an array.

Code:

		const isArray \= Array.isArray(\[1, 2, 3\]); // true

**Length()-\> return the length of an array** 	

	Start from 1 so for computer len=length-1

**at(index)-\>**  return the element value which is on given index

			

