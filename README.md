# Daily Notes

### December 8th, 2021
#### JavaScript: Object Oriented Programming

Today, I worked through the JavaScript Algorithms and Data Structures section, specifically the Object Oriented Programming course from freeCodeCamp.

An **Object** class is one of several data types in JavaScript. Objects are used to store data in the form of *Properties* and *Values*. Within an object, you can create several Properties and also assign Values to those properties.

For example:

```
let dog = {
    name: "Xena",
    color: "black",
    numLegs: 4
};
```

In the above code, we are creating an object called **dog**. The object **dog** has three properties: *name*, *color* and *numLegs* and each property is assigned a value.


### December 9th, 2021
#### Object Oriented Programming cont.

As I continue to learn about object oriented programming in JavaScript, it's clear to me just how useful it is. Today, I learned about **Prototypes** which are a property of objects that are used to create a template object. Think of prototypes as the base of a soup to which you can add your own indredients.

You can create a new object that inherits the prototype of a parent by using the `Object.creat(obj)` method. This method creates a new object and (obj) can be se the the prototype of the new object. In the example below, a new object called **ChildObject** inherits its prototype from **ParentObject**.

```
ChildObject.prototype = Object.create(ParentObject.prototype);
```

Additionally, you can give **ChildObject** its own methods/prototypes aside from its inherited ones. In the example below, we create a new prototype for **ChildObject** called **methodName** which is a function.

```
ChildObject.prototype.methodName = function() {

};
```

Say ChildObject inherits a prototype from ParentObject. Can you override the parent prototype? Yes! You can do this using the `ChildObject.prototype.methodName = ;` and by setting the methodName to the parent prototype you are trying to change.

On top of that, I have been introduced to the principle in programming called *Don't Repeat Yourself (DRY)*. The principle is exactly as the name states--try your best not to repeat code. This way, if a problem arises in your code, you won't have to fix every instance of that code.

#### Functional Programming

Functional programming is about verbs or actions. Object oriented programming is about nouns. The objective is to make "pure" functions 


### December 10th, 2021

Today, I began watching Bianca Gandolfo's [JavaScript: From Fundamentals to Functional JS, v2](https://frontendmasters.com/courses/js-fundamentals-functional-v2/) course on Frontend Masters.

Object assignment with dots:

You can use either method below to assign the object person with a key "name" with a value "Mrs. White".

```
var person = {};
    person.name = "Mrs. White";

var person = {
    name: "Mrs. White"
};
```

Learning notes:
- A **primitive value** is a string, number, boolean, null, undefined and NaN.
- A **non-primitive** value can be a function, array, object, etc.
- When you store a non-primitive value somewhere, it is passed by reference.
- Storing a value by reference or by value. Primitive values cannot be re-assigned. We store primitive values by value.
- Arrays are just objects. A big difference is that arrays have specific methods on them. Arrays also have a sorting and numbering to them as they are zero-index based.

Exercise 1: Creating a clue game and exercising different nested arrays.

```
let game = {};

game.murderer = "??";

game['weapons'] = [
    {type: "candlestick", location: "parlor"},
    {type: "lead pipe", location: "basement"},
    {type: "spoon", location: "kitchen"},
    {type: "harsh words", location: "heart"}
    ];

game.character = [];
game.character[0] = 'Miss Scarlet';
game.name.push('Mr. Green');

```


### December 13th, 2021

#### ES6 Destructuring
Allows you to assign multipe targets to multiple sources. This simplifies code and makes code less verbose.

```
const [first, second] = [true, false];
```

In the code above, two variables are declared within an array: first and second. Both variables are assigned in order to the values in the array to the right. First is assigned true and second is assigned false.

```
const {first, second} = {first = 0, second = 1}
```

In the code above, we are making variable declarations for objects. Since these are objects, you have to remember that unlike arrays, objects do not have an order. Thus, when you declare and assign values to objects in this way, the variable names have to match.


### December 15th, 2021

#### ES6 Destructuring cont.

##### Destructuring an array:
```
var [a, b] = [1, 2];
console.log(a, b); ==> 1 2
```
Variables 'a' and 'b' are created and assigned to the values in order to the array on the right. 


##### Swap variables easily without creating a temporary value:

```
var a = 1, b = 2;
```
How would you reassign the above values so that a = 2 and b = 1? Without destructing, you would have to create a temporary variable to store a in.
```
var a = 1, b = 2;
var temp = a;
a = b;
b = temp;
```
This can be done much faster using destructuring:
```
[b, a] = [a, b];
```

##### Destructuring objects examples

```
var {user: x} = {user: 3};
console.log(x);
// => 3
```

To assign a value to a property in an object via destructuring, property names must match. The code above will work but the code below does not.

```
var {user: x} = {user1: 3};
console.log(x);
// => undefined
```

