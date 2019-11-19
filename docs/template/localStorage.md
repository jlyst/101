# Local Storage
Enable data to be stored in the user's browser. [Demonstration](https://repl.it/@jimlyst/local-storage)


### JavaScript

Add the following function to your JavaScript file.

```js
function updateStorage() {
    localStorage.setItem("myStoredData", JSON.stringify(myData));
}
```

Update your `setup()` function to the following in order to get any locally stored data.

```js
function setup() {
  if (localStorage.getItem("myStoredData")) {
    myData = JSON.parse(localStorage.getItem("myStoredData"));
  }
  render();
}
```

Then add a call to this function `updateStorage()` wherever it is needed. For example, if you have any of the following functions you may want to add it at the end of the function code block.
- submit()
- deleteItem()
- toggleComplete()
