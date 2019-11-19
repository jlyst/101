# Mark Item (Like as a Favorite)
The following code modifications can enable a user to mark an item in the collection, as a favorite or completed item for example. [Demonstration](https://repl.it/@jimlyst/mark-item)


### JavaScript
Modify the HTML template in the `render` function to include the following element. You could change the font awesome icon and the property name as you like. For example you may want `item.favorite` instead.
```js
<i class="far fa-check-square ${item.complete ? '' : 'fade'}" onclick="toggleComplete(${index})"></i>
```


Your `render` function may end up looking something like this...
```js
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
```
Add a function to toggle a state. In this example we will toggle whether the item is complete. Again change this to favorite if you wish, but make sure it is consistent with changes in your render function.

```js
function toggleComplete(index) {
  if (myData[index].complete == true) {
    myData[index].complete = false;
  }
  else {
    myData[index].complete = true;
  }
  render();
}
```

### CSS

Add the following style to modify the icon on selection. You may choose to do something different to indicate the change by a user.
```css
.fade {
  opacity: .3;
}
```

You may want to modify your .item-actions style property like below, if you have two icons.
```css
grid-template-columns: 1fr 1fr;
```
