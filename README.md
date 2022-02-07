# Javascript Data types and Data structures with code samples
<br>
JavaScript has primitive and non-primitive data structures. Primitive data structures and data types are native to the programming language. These include boolean, null, number, string, etc. ... These include linear data structures, static data structures, and dynamic data structures, like queue and linked lists.
<br>

* # Data types
There are 8 data types that are currently exist in JavaScript.
<br>
1.string<br>
2.Number<br>
3.Boolean<br>
4.Null<br>
5.Undefined<br>
6.Symbol<br>
7.BigInt<br>
8.Object<br>

## 1.String:
The string type is used to represent textual data. It is a set of "elements" of 16-bit unsigned integer values. Each element in the String occupies a position in the String.
<br>
**Example:**<br>
a="name"  (Here name is now string)

## 2.Number:
Number type is a double-precision 64-bit binary format IEEE 754 value. There is not a specific type for integers.

The number type has three symbolic values: +Infinity, -Infinity, and NaN (not-a-number).
<br>
**Example:**<br>
42 / +0
(Infinity)<br>

42 / -0
(-Infinity)
## 3.Boolean:
Boolean represents a logical entity and can have two values: true and false.

**Example:**<br>
Boolean(10 > 9) <br>
(True)<br>
Boolean(10 < 9)<br>
(False)<br>
## 4.Null type:
The Null type has exactly one value: null. See null and Null for more details.

**Example:**<br>
var myVar = null;<br>
alert(myVar); <br>
(null type)<br>

## 5.Undefined:
A variable that has not been assigned a value has the value undefined. See undefined and Undefined for more details.

**Example:**<br>
var myVar;<br>
alert(myVar);<br> (undefined)

## 6.Symbol:
A Symbol is a unique and immutable primitive value and may be used as the key of an Object property (see below). In some programming languages, Symbols are called "atoms".

**Example:**<br>
const x = Symbol()<br>
typeof x;<br>  (symbol)
## 7.BigInt:
The BigInt type is a numeric primitive in JavaScript that can represent integers with arbitrary precision. With BigInts, you can safely store and operate on large integers even beyond the safe integer limit for Numbers.

A BigInt is created by appending n to the end of an integer or by calling the constructor.<br>
**Example:**<br>
const x = 2n ** 53n;
(9007199254740992n)<br>
const y = x + 1n;
(9007199254740993n)

## 8.Object:
An object is a value in memory which is possibly referenced by an identifier.<br>
In JavaScript, objects can be seen as a collection of properties. There are two types of object properties which have certain attributes: the data property and the accessor property.

* # Data structures:
There are 5 most important data structures are there namely:<br>
1.Stack <br>
2.Queue<br>
3.Linked list<br>
4.Set<br>
5.Hash table<br>

## 1.stack:
Stack follows the principle of LIFO (Last In First Out). If you stack books, the top book will be taken before the bottom one. Or when you browse on internet, the back button leads you to the most recently browsed page.<br>
Stack has these common methods:    
* push: input a new element
* pop : remove the top element, return the removed element
* peek : return the top element
* length : return the number of element(s) in Stackthese common methods:<br>

Array in Javascript has the attributes of Stack, but we construct a Stack from scratch by using function Stack()

**Example:**<br>
function Stack() {
this.count = 0;
  this.storage = {};

  this.push = function (value) {
    this.storage[this.count] = value;
    this.count++;
  }

  this.pop = function () {
    if (this.count === 0) {
      return undefined;
    }
    this.count--;
    var result = this.storage[this.count];
    delete this.storage[this.count];
    return result;
  }

  this.peek = function () {
    return this.storage[this.count - 1];
  }

  this.size = function () {
    return this.count;
  }
}<br>
## 2.Queue:
Queue is similar to Stack. The only difference is that Queue uses the FIFO principle (First In First Out). In other words, when you queue for bus, the first in the queue will always board first.<br>
Queue has following methods:<br>

* enqueue: enter queue, add an element at the end
* dequeue: leave queue, remove the front element and return it
* front: get the first element
* isEmpty: determine whether the queue is empty
* size: get the number of element(s) in queue

**Example:**<br>
function Queue() {
  var collection = [];
  this.print = function () {
    console.log(collection);
  }
  this.enqueue = function (element) {
    collection.push(element);
  }
  this.dequeue = function () {
    return collection.shift();
  }
  this.front = function () {
    return collection[0];
  }

  this.isEmpty = function () {
    return collection.length === 0;
  }
  this.size = function () {
    return collection.length;
  }
}<br>
## 3.Linked list:
Literally, a linked list is a chained data structure, with each node consisting of two pieces of information: the data of the node and the pointer to the next node. Linked list and conventional array are both linear data structures with serialised storage. Of course, they also have differences:<br>
A unilateral linked list normally has following methods:

* size: Return the number of node(s)
* head: Return the element of the head
* add: Add another node in the tail
* remove: Remove certain node
* indexOf: Return the index of a node
* elementAt: Return the node of an index
* addAt: Insert a node at a specific index
* removeAt: Delete a node at a specific index
  
**Example:**<br>
function LinkedList() {  
        var length = 0;  
        var head = null;  
        this.size = function () {    
            return length;  
        }  
        this.head = function () {    
            return head;
        }
}<br>
## 4.Set:
A set is a basic concept in mathematics: a collection of well defined and distinct objects. ES6 introduced the concept of set, which has certain level of similarity with array. However, a set does not allow repeating elements and is not indexed.
<br>

A typical set has methods as follows:<br>

* values: Return all elements in a set
* size: Return the number of elements
* has: Determine whether an element exists
* add: Insert elements into set
* remove: Delete elements from set
* union: Return the intersection of two sets
* difference: Return the difference of two sets
* subset: Determine whether a certain set is a subset of another set<br>
**Example:**<br>
function MySet() {  
    var collection = [];  
    this.has = function (element) {    
        return (collection.indexOf(element) !== -1);  
    }  
    this.values = function () {    
        return collection;
    }
}<br>
## 5.Hash table:
A hash table is a key-value data structure. Due to the lightning speed of querying a value through key, it is commonly used in Map, Dictionary or Object data structures. As shown in the graph above, the hash table uses a hash function to convert keys into a list of numbers, and these numbers serve as the values of corresponding keys. To get value using key is dashingly fast, time complexity can achieve O(1). The same keys must return the same values — this is the basis of the hash function.<br>
The hash table has the following methods:

* add: Add a key-value pair
* remove: Delete a key-value pair
* lookup: Find a corresponding value using a key<br>
**Example:**<br>
function HashTable() {<br>
  let storage = [];<br>
  const storageLimit = 4;<br>

  this.add = function (key, value) {<br>
    var index = hash(key, storageLimit);<br>
    if (storage[index] === undefined) {<br>
      storage[index] = [<br>
        [key, value]<br>
      ];<br>
    } <br>
}<br>

* # References:


https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures

https://codeburst.io/javascript-essentials-types-data-structures-3ac039f9877b

https://www.educative.io/blog/javascript-data-structures

https://betterprogramming.pub/8-common-data-structures-in-javascript-3d3537e69a27
