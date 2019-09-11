# JavaScript Intro

#### Summary and Objective


## INSTRUCTIONS

### 1 - Get the Starter Code

Create a new HTML/CSS/JS application. The code below assumes you will use `index.html`, `style.css`, and `script.js` in the same folder, like the default setup in [Repl.it](https://repl.it).

**HTML**

Replace your HTML with the following.

```html
<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width">
	<title>repl.it</title>
	<link href="style.css" rel="stylesheet" type="text/css" />
</head>
<body>
	<div class="app">
		<div class="nav-bar">
			<div class="nav-left">APP NAME</div>
			<div class="nav-right"><button>menu</button></div>
		</div>
		<div class="main-section">
			<div class="actions">
        <input class="main-input" placeholder="input placeholder">
        <button>Input Action</button>
      </div>
      <!--------------------------------------->
      <!-- OUR PROGRAM RESULTS WILL GO BELOW -->
      <!--------------------------------------->
      <div class="collection" id="results">
        Nothing to see here...
      </div>
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
  background-color: black;
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
> - 1
> - 2
