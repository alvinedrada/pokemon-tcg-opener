# Pokemon TCG Opener Easy Version

Pokemon is so awesome so go create a Pokemon trading card pack opener using HTML, CSS, and JS. This project will use skills you learned about DOM. The easy version will give you the template for the HTML and CSS so you will focus more on the Javascript.

An example of what the finished product may look like can be found here: https://pokemon-tcg-opener.alvin-edrada.repl.co/

## Difficulty
Intermediate

## Prerequisites
* HTML structuees and attributes
* Basic CSS styling
* Adding Elements in HTML using DOM
* Changing Elements in HTML using DOM
* Javascript functions
* Event listeners
* For loop

## Instructions

## Part I: Javascript

1. Create a reference to the element with the id```pokemon-pack-cover``` by using ```document.getElementById("yourElementId")```.

``` javascript
let pack = document.getElementById("yourElementId");
```

2. Create an event listener that runs a function called ```openPack``` when you click on the ```pokemon-pack-cover``` element.

``` javascript
pack.addEventListener("click", openPack);
```


3. Create a function called openPack() that generates pokemon cards images
* Inside the function, create a reference to the element with the id ```opened-pokemon-cards``` by using ```document.getElementById("yourElementId")```.

``` javascript
let cards = document.getElementById(yourElementId");
```

* Create a while loop that checks if the variable you just made has children. Copy the following code into the function.
 ``` javascript
  while (cards.firstChild) {
    cards.removeChild(cards.firstChild);
  }
 ```
  * The code above removes the HTML element that contains the pokemon cards if there is already children.
  
* Now we must create the cards that will be opened. Create a for loop that runs 10 times. You can copy and paste the code below. If you want to learn more about for loops: https://www.w3schools.com/js/js_loop_for.asp

  ``` javascript
  for (let cardNumber = 0; cardNumber < 10; cardNumber++) {

  }
  ```

  * Inside the for loop you will want to create a card each time the loop runs, so make an ```div``` element using DOM:
  ``` javascript
  var cardDiv = document.createElement("elementYouWantToCreate");
  ```
  
  * Add the ```pokemon-card``` CSS class to the newly created element. (https://www.w3schools.com/howto/howto_js_add_class.asp)
  ``` javascript
  cardDiv.classList.add("classYouWantToAdd");
  ```

  * create an ```img``` element using DOM, then set the ```id``` of the element to the ```cardNumber``` from the for loop.
  ``` javascript
  let cardImg = document.createElement("elementYouWantToCreate");
  cardImg.id = cardNumber;
  ```

  * Create a variable ```randomNumber``` and set it to a function called ```getRandomNumber(1, 102)``` (Because there are 102 cards in the card pool)
  ``` javascript
  let randomNumber = insertFunctionNameHere(1, 102);
  ```
  
  * Set the ```img``` element ```src``` to the image ```"pokemon-cards/pokemon-card-back.jpg"```
  
  * Create an event listener to the ```cardImg``` variable the calls a function ```flipCard(cardImg, randomNumber)``` to flip the cards and reveal what you got. You can copy and past the following code:
  ``` javascript
  cardImg.addEventListener("click", function() {
      flipCard(cardImg, randomNumber);
  });
  ```
  
  * Append the ```img``` element as a child to the ```div``` element you created in the very beginning together with DOM.
  ``` javascript
  cardDiv.appendChild(cardImg);
  ```
  
  * Append the ```div``` element as a child to the element with id ```opened-pokemon-cards``` with DOM (You made this in the very beginning of the openPack() function!)
  ``` javascript
  cards.appendChild(cardDiv);
  ```
  
4. Create the flipCard() function that takes in two parameters cardImg and num. An example of how to do this is below.
``` javacsript
function functionName(parameter1, parameter2) {
    // code
}
```

  * Inside the function, remove the event listener to prevent the card from being flipped again. You can copy the line of code below.
  ``` javascript
  cardImg.removeEventListener("click", flipCard);
  ```
  * Then, add a class called ```flipped``` to the cardImg parameter.
  ``` javascript
  cardImg.classList.???.("classToAdd");
  ```
  * Change the src of the cardImg parameter to the following:
  ``` javascript  
  "pokemon-cards/card-" + num + ".jpg";
  ```
    
    
5. Create the getRandomNumber function with 2 parameters, min and max
* Inside the function paste the following ```Math.floor(Math.random() * (max - min) + min);```. This generates a random integer between other integers. Your function can be copy and pasted from below.

``` javascript
function getRandomNumber(min, max) {
  return Math.floor(Math.random() * (max - min) + min);
}
```

## Stretch Goals
1. Some cards are known as "rare" meaning that only one come in each pack opened. Try making it so that you can open only one rare card per pack. The rare cards are the first 17 cards in ```/pokemon-cards```. (Hint: if and else loops)
2. Decorate with CSS!
