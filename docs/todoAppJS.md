# JavaScript for a To Do App

Using the HTML and CSS from your [previous work](gridBasedApp) on a "To-Do App", use this JavaScript as a starting point for an interactive application. You will want to adapt it based on your design choices in your HTML and CSS, and any features you prefer. Optionally, if you want to start anew with the HTML and CSS, you can use the HTML/CSS template at the bottom of this page.

> **IMPORTANT**: In your previously created HTML you will want to add the following...
> - `id="myInput"` to your `input` element.
> - `onclick="submit()"` to your clickable element (maybe a button) to submit a new todo
> - `id="results"` to your element with class "collection"

##### To-Do JavaScript Starter Code
```js
// Let's start with some default to-do items.
var myData = [
  {
    content: "Go to grocery.",
    complete: true
  },
  {
    content: "Call mom.",
    complete: false
  },
  {
    content: "Take dog to vet.",
    complete: false
  },
  {
    content: "Pay bills.",
    complete: false
  }
];


function setup() {
  if (localStorage.getItem("myStoredData")) {
    myData = JSON.parse(localStorage.getItem("myStoredData"));
  }
  render();
}

function render() {
  var myOutput = "";
  myData.forEach(function (item, index) {
    myOutput += `
      <div class="item">
        <div class="item-content">
          ${item.content}
        </div>
        <div class="item-actions">
          <i class="far fa-check-square ${item.complete ? '' : 'fade'}" onclick="toggleComplete(${index})"></i>
          <i class="far fa-trash-alt fade" onclick="deleteItem(${index})"></i>
        </div>
      </div>`;
  });
  document.querySelector("#results").innerHTML = myOutput;
}

function submit() {
  var newItem = document.querySelector("#myInput").value;
  myData.push({content: newItem, complete: false});
  updateStorage();
  render();
}

function deleteItem(index) {
  var verify = confirm("Are you sure? You are about to delete this item.");
  if (verify) {
    myData.splice(index, 1);
    updateStorage();
    render();
  }
}

function toggleComplete(index) {
  if (myData[index].complete == true) {
    myData[index].complete = false;
  }
  else {
    myData[index].complete = true;
  }
  updateStorage();
  render();
}

function updateStorage() {
    localStorage.setItem("myStoredData", JSON.stringify(myData));
}

window.onload = setup();
```

## A Few Things to Point Out

`document.querySelector("#results").innerHTML = myOutput;`

You will notice that the `render()` function will place the to-do items inside your `id="resluts"` HTML element, overwriting anything you had in there before. You can delete that content from your HTML if you like.

```
<div class="item-actions">
  <i class="far fa-check-square ${item.complete ? '' : 'fade'}" onclick="toggleComplete(${index})"></i>
  <i class="far fa-trash-alt fade" onclick="deleteItem(${index})"></i>
</div>
```

Notice that if an item is complete, a *class* of `fade` is applied to the check icon. Modify as you wish, since you likely don't have a CSS class for it. This also uses a [conditional (ternary) operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_Operator), `${item.complete ? '' : 'fade'}`, which is a very useful substitute for a "conditional if" statement. This allows you to toggle the look of the icon.

#### Local Storage

Notice we are using [localstorage](https://www.w3schools.com/jsreF/prop_win_localstorage.asp) to save To-Do items in the browser for the user. To store our object array it requires us to convert it into a JSON string.

## Optional HTML and CSS Templates

#### HTML
```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>repl.it</title>
    <link href="https://use.fontawesome.com/releases/v5.7.2/css/all.css" rel="stylesheet">
    <link href="style.css" rel="stylesheet" type="text/css" />
</head>

<body>
    <div class="app">
        <div class="nav-bar">
            <div class="nav-left">APP NAME</div>
            <div class="nav-right"><i class="fas fa-info-circle"></i></div>
        </div>
        <div class="main-section">
            <div class="actions">
                <input class="main-input" id="myInput" placeholder="input here" size="30">
                <i class="fas fa-arrow-circle-right" onclick="submit()"> </i>
            </div>
            <div class="collection" id="results">
                
            </div>
        </div>
    </div>
    <script src="script.js"></script>
</body>

</html>
```

#### CSS
```css
body {
  margin: 0;
  background: #eee;
}

.nav-bar {
  display: grid;
  grid-template-columns: 1fr 1fr;
  position: sticky;
  top: 0;
  background: black;
  color: white;
  padding: 11px;
  font-size: 22px;
}

.nav-right {
  text-align: right;
}

.actions {
  text-align: center;
  padding: 10px;
  background: lightgray;
  font-size: 20px;
  line-height: 30px;
}

.main-input {
  border: none;
  outline: none;
  border-radius: 99px;
  font-size: 20px;
  line-height: 30px;
  padding: 0px 15px;
}

.collection {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 10px;
  padding: 11px;
  margin: auto;
  max-width: 900px;
}

.item {
  display: grid;
  grid-template-rows: auto 35px;
  background: white;
  box-shadow: 1px 1px 5px black;
}

.fade {
  opacity: .3;
}

.item-content {
  border-bottom: 1px solid lightgray;
  min-height: 50px;
  text-align: center;
  background-color: #00a;
  color: white;
  padding: 7px;
}

.item-actions {
  display: grid;
  justify-items: center;
  align-items: center;
  grid-template-columns: 1fr 1fr;
}

.item-actions > * {
  place-self: stretch;
  text-align: center;
  line-height: 35px;
}

@media only screen and (max-width: 600px) {
  .collection {
    grid-template-columns: 1fr;
  }
}
```



