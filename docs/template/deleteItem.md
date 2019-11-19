# Delete Item from Collection
The following code modifications demonstrate how a user may delete items from a collection.[Demonstration[(https://repl.it/@jimlyst/delete-item)


### JavaScript

Add the following to your HTML template in your render function.
```js
<div class="item-actions">
  <i class="far fa-trash-alt fade" onclick="deleteItem(${index})"></i>
</div>
```

Your render function should end up looking something like this.
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
          <i class="far fa-trash-alt fade" onclick="deleteItem(${index})"></i>
        </div>
      </div>`;
  });
  document.querySelector("#results").innerHTML = myOutput;
}
```

Then add the `deleteItem` function below to your script.js file.

```js
function deleteItem(index) {
  var verify = confirm("Are you sure? You are about to delete this item.");
  if (verify) {
    myData.splice(index, 1);
    render();
  }
}
```

### CSS
Finally add some style properties for your new html elements. Adapt as you wish.
```css
.item-actions {
  display: grid;
  justify-items: center;
  align-items: center;
  grid-template-columns: 1fr;
}

.item-actions > * {
  place-self: stretch;
  text-align: center;
  line-height: 35px;
}
```
