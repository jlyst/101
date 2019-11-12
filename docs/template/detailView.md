# Add Detail View

With the following modifications, if a user clicks an item in the collection, a detailed view of that item will fill the screen with a close icon that allows the user to close the detail view and return to the collection view.

### JavaScript
First, you will want to have data that provides text for the list view, like `title` shown below, and text for a detail view, like `content` shown below.
```
var myData = [
  {
    title: "Title 1",
    content: "Content of card one."
  },
  {
    title: "Title 2",
    content: "Content of card two."
  }
];
```


Next you will want to modify your render function like below. Notice the item html template now includes `onclick="showDetail(${index})"` and we now display `item.title` on the card.
```
function render() {
  var myOutput = "";
  myData.forEach(function (item, index) {
    myOutput += `
      <div class="item" onclick="showDetail(${index})">
        <div class="item-content">
          ${item.title}
        </div>
      </div>`;
  });
  document.querySelector("#results").innerHTML = myOutput;
}
```

Add this new function to your JavaScript file. It is called when a user clicks an item card. Of course, you will eventually want to refine and style the output of your detail view defined in the `detail` variable string.
```
function showDetail(i){
  var element = document.createElement("div");
  element.classList.add("detail-view");
  var detail = `
    <div class="close-button" onclick="this.parentElement.remove()"><i class="fas fa-times"></i></div>
    <div>${myData[i].content}</div>
  `;
  element.innerHTML = detail;
  document.querySelector('body').appendChild(element);
}
```

### CSS
Add the following styles to your style.css file. This enables your detailed view to fill the screen.
```
.detail-view {
  position: absolute;
  top: 0;
  background: #fff;
  height: 100vh;
  width: 100vw;
  padding: 25px;
  box-sizing: border-box;
}

.close-button {
  font-size: 48px;
  text-align: right;
}
```

That's it. You should have detail view funcationality. 
