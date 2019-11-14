# The Core Web App Template

This is the core template used to demonstrate additional features in this collection. You can find a functioning example of this template [here](https://repl.it/@jimlyst/Core-Template).

### HTML (index.html)
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
		</div>
		<div class="main-section">
			<div class="collection" id="results">
        <!-- items will be inserted here with JavaScript -->
			</div>
		</div>
	</div>
	<script src="script.js">
	</script>
</body>

</html>
```

### CSS (style.css)
```css
body {
  margin: 0;
  background: #eee;
}

.nav-bar {
  position: sticky;
  top: 0;
  background: black;
  color: white;
  padding: 11px;
  font-size: 22px;
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
  background: white;
  box-shadow: 1px 1px 5px black;
}

.item-content {
  padding: 7px;
}

@media only screen and (max-width: 600px) {
  .collection {
    grid-template-columns: 1fr;
  }
}
```

### JavaScript (script.js)
```js
// Let's start with some default data.
var myData = [
  {
    content: "Go to grocery.",
  },
  {
    content: "Call mom.",
  },
  {
    content: "Take dog to vet.",
  },
  {
    content: "Pay bills.",
  }
];

// This is the first function to run when the page loads
function setup() {
  render();
}

// We will handle what is displayed in this function
function render() {
  var myOutput = "";
  myData.forEach(function (item, index) {
    myOutput += `
      <div class="item">
        <div class="item-content">
          ${item.content}
        </div>
      </div>`;
  });
  document.querySelector("#results").innerHTML = myOutput;
}

// This kicks things off once the page is loaded
window.onload = setup();
```
