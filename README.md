# Pokemon TCG Opener

Pokemon is so awesome so go create a Pokemon trading card pack opener using HTML, CSS, and JS.

## Difficulty
Intermediate

## Prerequisites
* HTML structuees and attributes
* Basic CSS styling
* Adding Elements in HTML using DOM
* Changing Elements in HTML using DOM
* Javascript looping
* Basic javascript (functions, strings)

## Instructions
1. Open the project in Replit (insert link) and create the following files:
  * index.html
  * styles.css
  * app.js
2. In your index.html file, initialize the file by copying and pasting the following:

``` html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>replit</title>
</head>

<body>

</body>

</html>
```

4. Link your CSS and JS files as follows.

``` html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>replit</title>
  <link href="style.css" rel="stylesheet" type="text/css" />
  <script src="script.js"></script>
</head>

<body>
  
</body>

</html>
```

## Part I: HTML
1. In your HTML file, create the following with the correct nested indented structure below. (The img should be nested inside of the div):
  * ```div``` with an id of "pokemon-pack-cover"
    * ```img``` with a src linked to "/pokemon-cards/pack-cover.png"
  * ```div``` with an id of "opened-pokemon-cards"

## Part II: CSS
1. Target the ```body``` element
  * Set the ```text-align``` to ```center```
2. Target the ```.pokemon-card``` class and the ```img``` element
  * Set the ```margin-top``` to ```10px``` (or however much you want)

## Part III: JS
1. Create a function that runs when the window loads (called an event). As shown below:
``` javascript
window.onload = function() {

}
```

* Store the ```pokemon-pack-cover``` element in a variable using the DOM method.
```document.getElementById(elementId)```. An example is shown below:

``` javascript
var yourVariableName = document.getElementById("yourElementId");
```
* Then, make an event listener that runs a function called ```openPack``` when you click on the ```pokemon-pack-cover``` element. (Make sure to change the variable and function names to be descriptive)

``` javascript
yourVariableName.addEventListener("click", openPack);
```

2. Create a function called openPack that generates pokemon cards images
* Inside the function, store the ```opened-pokemon-cards``` element in a variable using the DOM method.

* Create a while loop that checks if the variable you just made has children (hint: you can use element.firstChild or element.hasChildNodes() or element.childNodes.length > ?) 
  * And if the condition is true, remove all the children (https://developer.mozilla.org/en-US/docs/Web/API/Element/remove or https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild).
  
* Now we must create the cards that will be openedCreate a for loop that runs 11 times. For review: https://www.w3schools.com/js/js_loop_for.asp
  * Inside the for loop you will want to create a card each time the loop runs, so make an ```div``` element using DOM:
  ``` javascript
  var yourVariableName = document.createElement("div");
  ```
  * Add the ```pokemon-card``` CSS class to the newly created element. (https://www.w3schools.com/howto/howto_js_add_class.asp)
  * create an ```img``` element using DOM, then set the id of the element to the index of your for loop.
  * Create a variable num and set it to a function called getRandomNumber(1, 102) (Because there are 102 cards)
  * Set the ```img``` element ```src``` to the image associated with the random number generated. (The src should include the folder name ```pokemon-cards/card-???.jpg```
  * Append the img element as a child to the div element together with DOM
  * Append the div element as a child to the element with id ```opened-pokemon-cards``` with DOM
  
3. Create the getRandomNumber function with 2 parameters, min and max
* Inside the function paste the following ```Math.floor(Math.random() * (max - min) + min);```. This generates a random integer between other integers.

## Stretch Goals
1. Some cards are known as "rare" meaning that only one come in each pack opened. Implement opening only one rare card per pack. The rare cards are the first 17 cards in ```/pokemon-cards```. (Hint: if and else loops)
2. Use CSS styling to display your cards in different ways (ex: 2 rows of 5, 1 row of 10, etc.)
