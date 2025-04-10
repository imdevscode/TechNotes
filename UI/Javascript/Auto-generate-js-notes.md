# 1. Javascript Into

## Javascript History

→ Javascript(JS) was created by Netscape and in 1996 they submitted the
javascript code to ECMA (European Computer Manufacturer Association)
which was a Non-Profit organization.

→ Later they launched different version under ECMAScript:

- 1997 - ECMAScript 1

- 1998 - ECMAScript 2

- 1999 - ECMAScript 3

- ECMAScript 4 was not launched.

- 2009 - ECMAScript 5

- 2011 - ECMAScript 5.1

- 2015 - **ECMAScript 2015 (ES6)** -- major update

- 2016 - ECMAScript 2016 (ES7) -- minor update

- 2017 - ECMAScript 2017 (ES8) -- minor update

- 2018 - ECMAScript 2018 (ES9) -- minor update

## “let” and “const”

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr>
<td><strong>var</strong></td>
<td><strong>Let</strong></td>
<td><strong>const</strong></td>
</tr>
<tr>
<td>It is function scoped.</td>
<td>It is block scoped.</td>
<td>It is block scoped.</td>
</tr>
<tr>
<td><p>Updated = Yes</p>
<p>Re-declared = Yes in scope.</p></td>
<td><p>Updated = Yes</p>
<p>Re-declared = No in scope</p></td>
<td><p>Updated = No</p>
<p>Re-declared = No</p></td>
</tr>
<tr>
<td>can be declared without initialization.</td>
<td>can be declared without initialization.</td>
<td>Can NOT be declared without initialization.</td>
</tr>
<tr>
<td>can be accessed without initialization as its default value is
“undefined”.</td>
<td>Can NOT be accessed without initialization as No default value.</td>
<td>Can NOT be accessed without initialization as No default value.</td>
</tr>
</tbody>
</table>

**<u>Example:-</u>**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><strong>function</strong> <strong>checkVar</strong>(){<br />
<strong>var</strong> a =10;<br />
<strong>if</strong>(true) { <strong>var</strong> a=20; console.log(a);
}<br />
console.log(a);<br />
}<br />
checkVar()</td>
</tr>
</tbody>
</table>

**<u>Output</u>**

20

20

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><strong>function</strong> <strong>checkLet</strong>(){<br />
<strong>let</strong> a =10;<br />
<strong>if</strong>(true) { <strong>let</strong> a=20; console.log(a);
}<br />
console.log(a);<br />
}<br />
<br />
checkLet()</td>
</tr>
</tbody>
</table>

**<u>Output</u>**

20

10

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><strong>function</strong> <strong>testLet</strong>(){<br />
<strong>let</strong> c=25;<br />
<strong>let</strong> c=30; <em><strong>//SyntaxError: Identifier 'c1'
has already been declared</strong></em><br />
console.log(c);<br />
}</td>
</tr>
</tbody>
</table>

## Template Strings

→ It allows to use variable in string enclosed under Back tick(present
under ESC key) using ${variable_name}.

|  |
|------------------------------------------------------------------------|
| **let** show = "Name is " + name + " Age is " + age + " City is " + city + "."; |

**<u>Using Template string</u>**

|                                                                      |
|----------------------------------------------------------------------|
| **let** show = \`Name is ${name}. Age is ${age}. City is ${city}.\`; |

## JS Data Types

→ JS is dynamically typed language, so it doesn't need explicitly
declare type of variable. The JS engine will automatically determine the
data type based on assigned value.

→ JS categorize Data types into two parts: Primitive & Non-Primitive.

### Primitive Data types

→ Primitive data type includes: Number, String, Bollean, Null, Undefined
& Symbol.

→ Primitive data type can hold single value.

→ All primitive are immutable, meaning their value once assigned can't
be changed. like below:

let age = 25;

age = 30; //this will be save as separate variable in memory.

#### Difference between Null & Undefined

→ Undefined means a variable has been declared but has not yet been
assigned a value.

→ Null means that a variable has been declared and assigned value Null.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>let age = null;</strong></p>
<p><strong>let x;</strong></p>
<p><strong>console.log(age); <em>// null</em></strong></p>
<p><strong>console.log(x); <em>// undefined</em></strong></p></td>
</tr>
</tbody>
</table>

### Non-Primitive Data types

→ Non-Primitive data type includes: Object, Array, Function, Date.

→ Non-Primitive can hold multiple values.

→ Non-Primitive are mutable & their value can be changed in the same
memory location.

#### Object 

→ object is collection of properties. These properties contain name &
value.

→ The object properties can be of type Number, String, Array or Function
as well.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>//object constructor</strong></em></p>
<p><strong>let obj1 = new object();</strong></p>
<p><em><strong>//create empty JS object</strong></em></p>
<p><strong>let obj2 = {};</strong></p>
<p><em><strong>//Create &amp; initialize object</strong></em></p>
<p><strong>let person = {</strong></p>
<p><strong>name: "Dev",</strong></p>
<p><strong>age: 25,</strong></p>
<p><strong>grades: ["A", "B", "C"],</strong></p>
<p><strong>intro: function {</strong></p>
<p><strong>console.log(`My name: ` + this.name);</strong></p>
<p><strong>}</strong></p>
<p><strong>};</strong></p>
<p><em><strong>//calling object method</strong></em></p>
<p><strong>person.intro();</strong></p></td>
</tr>
</tbody>
</table>

#### Array

→ Array is special kind of object which store collection of values which
can be of any type.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>let numbers = [1, 2, 3, 4, 5];</strong></p>
<p><em><strong>//array with multiple type elements</strong></em></p>
<p><strong>let mixedArray = [1, "two", { name: "Object" }, [3, 4,
5]]</strong>;</p></td>
</tr>
</tbody>
</table>

#### Functions

→ Function is also Non-primitive data type, i.e their value can be
changed in the same memory location.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>//myFunc variable is of type
Function</strong></em></p>
<p><strong>let myFunc = function { console.log('Hello world');
}</strong></p>
<p><em><strong>//JS arrow func without parameters</strong></em></p>
<p><strong>let arrowFunc = () =&gt; {</strong></p>
<p><strong>console.log('Hello world');</strong></p>
<p><strong>}</strong></p></td>
</tr>
</tbody>
</table>

## JS Array Methods

### map()

→ map() method is used to create new array from existing array.

|                                            |
|--------------------------------------------|
| **var new_arr = arr.map(func \[, args\])** |

→ It apply function passed as paramter to each element of array. \\

→ Ex:- using map to return square of each array element.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>let arr = [1,2,3,4];</strong></p>
<p><strong>let sqr = arr.map(item =&gt; item * item);</strong></p>
<p><strong>console.log(sqr); <em>// [1,4,9,16]</em></strong></p></td>
</tr>
</tbody>
</table>

→ function to get Full name

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>const person = [</strong></p>
<p><strong>{fname: "Shaun", lname: "Matt"},</strong></p>
<p><strong>{fname: "Todd", lname: "Josh"},</strong></p>
<p><strong>{fname: "Dev", lname: "Dhingra"},</strong></p>
<p><strong>]</strong></p>
<p><strong>function getFullName(item){</strong></p>
<p><strong>return [item.fname, item.lname].join(" ");</strong></p>
<p><strong>}</strong></p>
<p><strong>console.log(person.map(getFullName));</strong></p>
<p><em><strong>// Output: ["Shaun Matt", "Todd Josh", "Dev
Dhingra"]</strong></em></p>
<p><strong>const fullName = person.map(item =&gt; [item.fname,
item.lname].join(“ “));</strong></p>
<p><strong>console.log(fullName);</strong></p>
<p><em><strong>// Output: ["Shaun Matt", "Todd Josh", "Dev
Dhingra"]</strong></em></p></td>
</tr>
</tbody>
</table>

### reduce()

→ reduce function apply on array elements and reduces the return
elements (also can be single element) based on callback function.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>array.reduce(function(accumulator, currentValue),
initValue)</strong></p>
<p><em><strong>/*</strong></em></p>
<p><em><strong>accumulator -&gt; Required. Previously returned value of
the function.</strong></em></p>
<p><em><strong>currentItem -&gt; Required. Item of the current
element.</strong></em></p>
<p><em><strong>currentIndex -&gt; Optional. Index of the current
element.</strong></em></p>
<p><em><strong>arr -&gt; Optional. Array the current element belongs
to.</strong></em></p>
<p><em><strong>initValue -&gt; Optional. Initial value to be passed to
function.</strong></em></p>
<p><em><strong>*/</strong></em></p></td>
</tr>
</tbody>
</table>

→ Eg: find sum of array elements.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>//array.reduce(function(accumulator, currentValue),
initValue);</strong></em></p>
<p><strong>const arr = [1,2,3,4];</strong></p>
<p><strong>let result = arr.reduce(function (sum, item) {</strong></p>
<p><strong>return sum + item;</strong></p>
<p><strong>}, 0);</strong></p>
<p><em><strong>//here initValue=0, means it will start from 0
index</strong></em></p>
<p><strong>console.log(result); <em>//output:- 10</em></strong></p></td>
</tr>
</tbody>
</table>

### filter()

→ filter() method also applies condition on array elements, if the
condition=true then elements gets pushed to output array else not.

Eg:- Return only even numbers

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>let nbr = [1,2,3,4,5,6];</strong></p>
<p><strong>function getEven(items)</strong></p>
<p><strong>{</strong></p>
<p><strong>return items%2 == 0;</strong></p>
<p><strong>}</strong></p>
<p><strong>let even = nbr.filter(getEven);</strong></p>
<p><strong>console.log(even); <em>// [2,4,6]</em></strong></p></td>
</tr>
</tbody>
</table>

→ return students whose marks greater then 90

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>const students = [</strong></p>
<p><strong>{ name: "Mark", marks: 80 },</strong></p>
<p><strong>{ name: "Dev", marks: 95 },</strong></p>
<p><strong>{ name: "Todd", marks: 75 },</strong></p>
<p><strong>{ name: "Max", marks: 96 }</strong></p>
<p><strong>];</strong></p>
<p><strong>let nintyMarks = students.filter( item =&gt; item.marks &gt;
90);</strong></p>
<p><strong>console.log(nintyMarks);</strong></p>
<p><em><strong>// [{ name: "Dev", marks: 95 }, { name: "Max", marks: 96
}]</strong></em></p></td>
</tr>
</tbody>
</table>

## forEach() in JS

→ It neither return new array nor modify the original array as it
iterate the array & perform action on each of it's element.

|                                                                  |
|------------------------------------------------------------------|
| **array.forEach(function(currentValue, index, arr), thisValue)** |

Here, function() → function to run on each element. (Required)

currentValue → value of current array element . (Required)

index → index of current array element. (Required)

arr → reference to Array itself. (Optional)

thisValue → this value. (Optional)

**<u>Example</u>**

1\. Compute sum of Array element

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>//myFunc variable is of type
Function</strong></em></p>
<p><strong>let myFunc = function { console.log('Hello world');
}</strong></p>
<p><strong>let arr = [10, 20, 30];</strong></p>
<p><strong>let sum = 0;</strong></p>
<p><strong>arr.forEach((item) =&gt; sum += item;);</strong></p></td>
</tr>
</tbody>
</table>

2\. Copy element of Array to another array.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>let arr1 = [1,2,3,4,5];</strong></p>
<p><strong>let arr2 = [];</strong></p>
<p><strong>arr1.forEach(copyArray);</strong></p>
<p><em><strong>//JS Hoisting will make this function declaration on top
at run time.</strong></em></p>
<p><strong>function copyArray(item) {</strong></p>
<p><strong>arr2.push(item);</strong></p>
<p><strong>console.log(`Element {item} pushed to new
array`);</strong></p>
<p><strong>}</strong></p></td>
</tr>
</tbody>
</table>

3\. Append "Hello" to each element

→ Though this can be achieved by array map() function as well.

|                                         |
|-----------------------------------------|
| **arr.map(item =\> \`Hello {item}\`);** |

Here we can implement using two approach:

→ function is passed array reference

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>let arr = [1, 2, 3];</strong></p>
<p><strong>arr.forEach((item, index, refArr) =&gt; {</strong></p>
<p><strong>refArr[index] = `Hello {item}`;</strong></p>
<p><strong>}</strong></p></td>
</tr>
</tbody>
</table>

→ passing forEach second argument "this"

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>arr.forEach(append(item, index) {</strong></p>
<p><strong>this[index] = `Hello {item}`;</strong></p>
<p><strong>}, arr);</strong></p></td>
</tr>
</tbody>
</table>

## Javascript Nested Functions 

→ In js, Functions can have one or more Nested functions. These inner
functions can access variable & parameters of outer fn.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>function outerfn(x) {</strong></p>
<p><strong>let z = 2;</strong></p>
<p><strong><mark>return</mark> (function innerfn(y) { <em>// inner
function</em></strong></p>
<p><strong>return x + y + z; <em>// use variables &amp; parameters from
outer fn</em></strong></p>
<p><strong>}); <em>// you can even return a function.</em></strong></p>
<p><strong>}</strong></p>
<p><strong>console.log(outerfn(4)(3)); <em>//Output: 9</em></strong></p>
<p><strong>let add = outerfn(4); <em>// function stored in variable
"add"</em></strong></p>
<p><strong>console.log(add(5)); <em>//Output: 11</em></strong></p></td>
</tr>
</tbody>
</table>

## Arrow function () =\> {}

**(parameter) =\> { function_body }**

→ They are also called <u>fat arrow(=\>)</u> function. Other programming
languages call it <u>lambda function</u>.

**<u>Regular function:</u>**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><strong>function</strong> <strong>addSum</strong>(a,b) {
<strong>return</strong> a+b; }<br />
console.log(addSum(5,5<strong>));</strong> <em><strong>//Output
10</strong></em></td>
</tr>
</tbody>
</table>

**<u>Arrow function</u>**

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><strong>let</strong> addSumLet = (a,b) =&gt; {
<strong>return</strong> a+b; }<br />
console.log(addSumLet(6,6)); <em><strong>//Output 12</strong></em><br />
addSumLet = (a,b,c) =&gt; { <strong>return</strong> a+b+c; }<br />
console.log(addSumLet(6,6,6)); <em><strong>//Output
18</strong></em></td>
</tr>
</tbody>
</table>

## JavaScript Scope

→ scope determines accessibility of variables. JS has 3 types of scope:

1.  Global scope 2) Function scope **3) Block scope**

→ Before ES6 variables had only Global & Function scope, but ES6
introduced two new keywords “let” & “const” which provide **Block
scope**.

→ variables declared inside a **block { }** can not be accessed from
outside the block.

→ but variables declared with "var" keyword can NOT have Block scope.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>{</strong></p>
<p><strong>let l = 2;</strong></p>
<p><strong>var v = 5; //var can NOT have block scope.</strong></p>
<p><strong>}</strong></p>
<p><strong>console.log(l); //l is block scoped, can’t be
accessed</strong></p>
<p><strong>console.log(v); //v CAN be accessed here: 5</strong></p></td>
</tr>
</tbody>
</table>

<img src="media/image1.jpg" style="width:6.5in;height:3.20833in" />

## JS Hoisting

→ Hoisting is JS behavior where **<u>function & variable</u>**
declarations are moved to top of their respective scopes in the
compilation phase.

→ This allows regardless of where they are declared, these functions &
variables can be accessed throughout that scope.

<img src="media/image2.jpg" style="width:6.11979in;height:1.01016in" />

### 

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>//function hoisting</strong></em></p>
<p><strong>myFunction(); <em>//here function is used before
declaring</em></strong></p>
<p><strong>function myFunc() {</strong></p>
<p><strong>console.log(“Hello”);</strong></p>
<p><strong>}</strong></p>
<p><em><strong>//variable hoisting</strong></em></p>
<p><strong>x=10; <em>//variable initialization</em></strong></p>
<p><strong>console.log(x); <em>//variable usage</em></strong></p>
<p><strong>var x; <em>//variable declaration</em></strong></p></td>
</tr>
</tbody>
</table>

|                                                |
|:----------------------------------------------:|
| ***Declaration –\> Initialisation –\> Usage*** |

### Only declarations are hoisted, & not initialization.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>// var code (global)</strong></em></p>
<p><strong>console.log(name); <em>//undefined</em></strong></p>
<p><strong>console.log(city); <em>//ReferenceError: name is not
defined</em></strong></p>
<p><strong>var name = 'Mukul Latiyan';</strong></p>
<p><strong>let city = “Delhi”;</strong></p></td>
</tr>
</tbody>
</table>

→ Above, will give Error as Initialisation can not be hoisted, only
Declaration can be hoisted so variable should be initialized before
usage. At compile-time this will be interpreted as:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>// how interpreter sees the above
code</strong></em></p>
<p><strong>var name;</strong></p>
<p><strong>let city;</strong></p>
<p><strong>console.log(name); <em>//undefined</em></strong></p>
<p><strong>console.log(city); <em>//ReferenceError: name is not
defined</em></strong></p>
<p><strong>name = 'Mukul Latiyan';</strong></p>
<p><strong>City = “Delhi”;</strong></p></td>
</tr>
</tbody>
</table>

### Hoisting var, let

→ hoisting allows variables declared with **“var”** to be accessed
before declaration, but not those declared with “**let**” or
“**const**”.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>function demoHoist() {</strong></p>
<p><strong>a = 10;</strong></p>
<p><strong>let b = 50;</strong></p>
<p><strong>}</strong></p>
<p><strong>demoHoist();</strong></p>
<p><strong>console.log(a); <em>//10</em></strong></p>
<p><strong>console.log(b); <em>//ReferenceError : b is not
defined</em></strong></p></td>
</tr>
</tbody>
</table>

→ Above, as “a” declaration not defined so will be considered declared
as “**var**” globally.

But “b” is declared by let so have scope in the function only.

## Javascript prototype Property

→ JS prototype property allow to add new properties (or method) to
object.

→ prototype is available with all javascript objects like Array.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><em><strong>//Creating Person object using function
constructor</strong></em></p>
<p><strong>function Person(name, year, city) {</strong></p>
<p><strong>this.name = name;</strong></p>
<p><strong>this.yearofBirth = year;</strong></p>
<p><strong>this.city = city;</strong></p>
<p><strong>this.grades = ['A', 'B', 'C'];</strong></p>
<p><strong>}</strong></p>
<p><strong>Person.prototype.nationality = "Indian";</strong></p>
<p><strong>Person.prototype.calculateAge = () =&gt; {</strong></p>
<p><strong>console.log('Age: {2024-this.yearofBirth}`);</strong></p>
<p><strong>}</strong></p></td>
</tr>
</tbody>
</table>

→ When any object property(or method) are called it first checks them in
the object & if not found the search in the object's prototype.

→ object prototype allow to **add new functionality** to existing object
like inheritance.

→ Object created using function constructor, inherits all it's prototype
Properties & methods.

→ Ex:- below two objects person1 & person2 created using same above
function constructor, so will inherit it's prototype nationality
property & calculateAge() method.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>const person1 = new Person('Dev', '1984',
'Delhi');</strong></p>
<p><strong>const person2 = new Person('Harit', '1985',
'Pune');</strong></p>
<p><strong>console.log(person1.nationality);</strong></p>
<p><strong>console.log(person2.nationality);</strong></p>
<p><strong>person1.calculateAge();</strong></p>
<p><strong>person2.calculateAge();</strong></p></td>
</tr>
</tbody>
</table>

### Array prototype

→ In Array as well new properties can be added using prototype.

→ Ex, add UpperCase method to Array.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr>
<td><p><strong>Array.prototype.toArrayUpperCase = function()
{</strong></p>
<p><strong>for(let i=0; i&lt;this.length; i++)</strong></p>
<p><strong>this[i] = this[i].toUpperCase();</strong></p>
<p><strong>};</strong></p>
<p><strong>let arr = ['car', 'boy', 'dog'];</strong></p>
<p><strong>arr.toArrayUpperCase(); <em>//['CAR', 'BOY',
'DOG']</em></strong></p></td>
</tr>
</tbody>
</table>
