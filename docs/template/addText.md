# Add Text Input
With the following modifications to the core template, a user can add a text item to the collection. 
[Demonstration](https://repl.it/@jimlyst/add-text).

### HTML
Add the following HTML to your index.html file just below the navigation element.

```html
<div class="actions">
  <input class="main-input" id="myInput" placeholder="input here" size="30">
  <i class="fas fa-arrow-circle-right" onclick="submit()"> </i>
</div>
```
### CSS
Add the following CSS to your style.css file as a starting point for your input style.

```css
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
```

### JavaScript
Add the following function to handle the submission of the text and save it to your data array.

```js
function submit() {
  var newItem = document.querySelector("#myInput").value;
  myData.push({content: newItem});
  render();
}
```
