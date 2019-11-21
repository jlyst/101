# Below are some miscellaneous code samples that may be useful.

### Shuffle an Array of Objects

```js
function shuffle(array) {
  for (let i = array.length - 1; i > 0; i--) {
    let j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
}
```
credit: https://javascript.info/task/shuffle

### Sort an Array of Objects

```js
const bands = [
  { genre: 'Rap', band: 'Migos', albums: 2},
  { genre: 'Pop', band: 'Coldplay', albums: 4},
  { genre: 'Rock', band: 'Breaking Benjamins', albums: 1}
];

function compare(a, b) {
  // Use toUpperCase() to ignore character casing
  const genreA = a.genre.toUpperCase();
  const genreB = b.genre.toUpperCase();

  let comparison = 0;
  if (genreA &gt; genreB) {
    comparison = 1;
  } else if (genreA &lt; genreB) {
    comparison = -1;
  }
  return comparison;
}

bands.sort(compare);
```
credit: https://www.sitepoint.com/sort-an-array-of-objects-in-javascript/

### Fiter an Array of Objects

```js
var heroes = [
	{name: “Batman”, franchise: “DC”},
	{name: “Ironman”, franchise: “Marvel”},
	{name: “Thor”, franchise: “Marvel”},
	{name: “Superman”, franchise: “DC”}
];

var marvelHeroes =  heroes.filter(function(hero) {
	return hero.franchise == “Marvel”;
});
```
credit: https://alligator.io/js/filter-array-method/
