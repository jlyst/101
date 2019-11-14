# Flip Cards

These code samples explain how to alter the Core Web Template to create flip card items within the collection. This code is an adaptation of https://www.w3schools.com/howto/howto_css_flip_card.asp. You can find a functioning example of this template [here](https://repl.it/@jimlyst/Core-Template-Flip-Cards).


### JavaScript
Since the flip card will have a front and back side, ensure that your data provides content for each card. Replace your data variable content with the following. Adapt as needed.
```js
var myData = [
  {
    front: "Card 1 Front",
    back: "Card 1 Back"
  },
  {
    front: "Card 2 Front",
    back: "Card 2 Back"
  }
];
```

Next, inside your render function modify the HTML template added to the `myOutput` variable (inside the forEach) to match what is shown below. You likely do not want to copy and paste this whole function if you have already modified your app from the Core Template. Adapt as needed.
```js
function render() {
  var myOutput = "";
  myData.forEach(function (item, index) {
    myOutput += `
      <div class="item flip-card">
        <div class="flip-card-inner">
          <div class="flip-card-front">
            ${item.front}
          </div>
          <div class="flip-card-back">
            ${item.back}
          </div>
        </div>
      </div>`;
  });
  document.querySelector("#results").innerHTML = myOutput;
}
```
### CSS
Add the following styles to your style.css file. It is recommended to put it just after the `.collection` style for organization purposes.

```css
.flip-card {
  background-color: transparent;
  height: 200px;
  perspective: 1000px;
}

.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 0.6s;
  transform-style: preserve-3d;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
}

.flip-card:active:hover .flip-card-inner {
  transform: rotateY(180deg);
}

.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
}

.flip-card-front {
  background-color: #bbb;
  color: black;
}

.flip-card-back {
  background-color: #2980b9;
  color: white;
  transform: rotateY(180deg);
}
```
You can remove the `.item` and `.item-content` styles since it will no longer be used.

#### That's it. You should have working flip cards!
