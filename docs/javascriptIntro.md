# JavaScript Intro

#### Summary and Objectives
In this activity you will step through methods for changing the browser view of the HTML dynamically with JavaScript programming. You will primarily use variables (as Strings and Arrays), functions, and for loops to enable an interactive applicaiton.

## INSTRUCTIONS

### 1 - Get the Starter Code

The code below assumes you will use the filenames `index.html`, `style.css`, and `script.js` in the same folder, like the default setup in [Repl.it](https://repl.it). We will start with an empty JavaScript file (script.js).

**HTML**

Replace your HTML with the following.

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
            <div class="nav-right"><i class="fas fa-bars"></i></div>
        </div>
        <div class="main-section">
            <div class="actions">
                <input class="main-input" placeholder="input here" size="30">
                <i class="fas fa-arrow-circle-right"> </i>
            </div>
            <!--------------------------------------->
            <!-- OUR PROGRAM RESULTS WILL GO BELOW -->
            <!--------------------------------------->
            <div class="collection" id="results">
                Nothing to see here yet...
            </div>
            <!--------------------------------------->
            <!--------------------------------------->
            <!--------------------------------------->
        </div>
    </div>
    <script src="script.js"></script>
</body>

</html>
```

**CSS**

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
  background: white;
  box-shadow: 1px 1px 5px black;
}

.item-content {
  border-bottom: 1px solid lightgray;
  height: 150px;
  background-color: #00a;
  color: white;
  padding: 7px;
}

.item-actions {
  display: grid;
  height: 50px;
  justify-items: center;
  align-items: center;
  grid-template-columns: 1fr 1fr 1fr;
}

@media only screen and (max-width: 600px) {
  .collection {
    grid-template-columns: 1fr;
  }
}
```

> <i class="fas fa-check-circle"></i> **CHECKPOINT**
> 
> When you run the application in the browser you should see a result similar to the one below.
> 
> ![App Images](images/jsStarterResult.png)

&nbsp;

### 2 - Use JavaScript to Insert Content

Notice that are starting code is basically like our last exercise with CSS grids with a subtle difference. Look in your HTML and find the following chunk of code.

```html
<!--------------------------------------->
<!-- OUR PROGRAM RESULTS WILL GO BELOW -->
<!--------------------------------------->
<div class="collection" id="results">
    Nothing to see here yet...
</div>
<!--------------------------------------->
<!--------------------------------------->
<!--------------------------------------->
```

First of all, all those lines that start with `<!--` and end with `-->` are just comments that do not affect the output. Comments just help people looking at the code.  You will notice that the `div` tag for our *collection* not only has a class, as before, but now has an *id* of *results*. ID's are similar to *classes* but are intended to identify one element rather than a type (or class) of elements for styling. The *id* will be used to select an element in the JavaScript to manipulate it.

In your JavaScript (script.js) insert the following line of code and run it.

```js
document.querySelector("#results").innerHTML = "Hello World";
```

You should see "Hello World" on your page now. It has been inserted inside your *results* element. Let's break down how that one line of code works.

- `document` is a JavaScript object that provides many useful methods to work with the HTML (the document). The period `.` can then be followed with one of many methods or properties for the document.
- `querySelector("#results")` is a method to basically go find an HTML element with an *id* of *results*. The `#` denotes an *id*, just like how you used `.` in CSS to prefix a class selector.
- `innerHTML` allows you to either *read* the HTML inside that element or *set* the HTML to something else. Here we set the HTML to be "Hello World". Note: Strings (a group of characters) need to have quotations around them.

Go ahead and change the *string* to something else. You can also use numbers without quotations and even do some math. Try `3 + 2`. You should see 5 in your web page view.
