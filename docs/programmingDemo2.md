## A Programming Demo

Each block of JavaScript below can be run in a nodeJS repl.it. It is recommended that you copy and paste the code and make changes to build a better understanding of how things work. 

### 1. Basic variables

```js
var name = "Jill";
var age = 28;
var isStudent = false;

var textOut = name + " is " + age + " years old. ";

console.log(textOut);
```
##### Result
> Jill is 28 years old.


### 2. Let's use a template literal to do the same thing (using \`backticks\` instead of quotation marks)

```js
var name = "Jill";
var age = 28;
var isStudent = false;

var textOut = `${name} is ${age} years old. `;

console.log(textOut);
```
##### Result
> Jill is 28 years old.

### 3. Use conditional statements to make a natural explanations of student status and driving status.

```js
var name = "Jill";
var age = 28;
var isStudent = false;

var studentText = "";
var drivingText = "";

if (isStudent) {
  studentText = "is a student";
}
else {
  studentText = "is not a student";
}

if (age >= 16) {
  drivingText = "can drive";
}
else {
  drivingText = "cannot drive";
}

var textOut = `${name} is ${age} years old and ${studentText}. ${name} ${drivingText}.`;

console.log(textOut);
```

##### Result
> Jill is 28 years old and is not a student. Jill can drive.

### 4. Let's use an object instead to describe our person.

```js
var person = {
  name: "John",
  age: 22,
  isStudent: true
}

var studentText = "";
var drivingText = "";

if (person.isStudent) {
  studentText = "is a student";
}
else {
  studentText = "is not a student";
}

if (person.age >= 16) {
  drivingText = "can drive";
}
else {
  drivingText = "cannot drive";
}

var textOut = `${person.name} is ${person.age} years old and ${studentText}. ${person.name} ${drivingText}`;

console.log(textOut);
```
##### Result
> John is 22 years old and is a student. John can drive

### 5. Let's use an array.

```js
var toDos = ["Grocery shop.", "Pay bills.", "Feed dog.", "Call mom.", "Read a great book."];

var count = toDos.length;

var firstThing = toDos[0];
var secondThing = toDos[1];

var textOut = `There are ${count} items to do. ${firstThing} ${secondThing} ...`;

console.log(textOut);
```

##### Result
> There are 5 items to do. Grocery shop. Pay bills. ...

### 6. Let's use a loop to display all to do items.

```js
var toDos = ["Grocery shop.", "Pay bills.", "Feed dog.", "Call mom.", "Read a great book."];

var textOut = "";

for (var i = 0; i < toDos.length; i++) {
  textOut += toDos[i] + " ";
}

console.log(textOut);
```

##### Result
> Grocery shop. Pay bills. Feed dog. Call mom. Read a great book.

### 7. Let's use another way to loop.

```js
var toDos = ["Grocery shop.", "Pay bills.", "Feed dog.", "Call mom.", "Read a great book."];

textOut = "";

toDos.forEach(function (item, index){
  textOut += item + " ";
});

console.log(textOut);
```

##### Result
> Grocery shop. Pay bills. Feed dog. Call mom. Read a great book.

### 8. Let's use an array of objects.

```js
var toDos = [
  {
    content: "Grocery shop.",
    complete: false
  },
  {
    content: "Pay bills.",
    complete: false
  },
  {
    content: "Feed dog.",
    complete: true
  },
  {
    content: "Call mom.",
    complete: false
  },
  {
    content: "Read a great book.",
    complete: false
  }
];

textOut = "";

toDos.forEach(function (item, index){
  if (!item.complete){
    textOut += `${item.content} `;
  }
});

console.log(textOut);
```

##### Result
> - Grocery shop.
> - Pay bills.
> - Call mom.
> - Read a great book.
