## Website Performance Optimization portfolio project

Critical Rendering Path
In order the achieve the goal of 90 or above PageSpeed, I made the following changes to index.html:
- added print media query to the stlesheet that was only needed when printing
- added media query based on screen size to the googlefonts style sheet in order to not have it downloaded for smaller mobile devices
- inlined the CSS and minified it
- downloaded googlefonts stylesheet locally and minified it
- minified the print sylesheet
- updated index.html to use minified files
- added async parameter to google anyalytics javascript
- downloaded all images locally
- optimized the images

Framerate Optimizations
In order to achieve a fps of greater than 60, I made the following updates in main.js
- In the onload function, I made the following changes
--- moved elem declaration outside of for loop
--- replaced querySelector with getElementByID
--- created a variable outside of for loop for movingPizzas element instead of querying document tree every iteration
--- declared an items array variable outside of the funtion that was then updated each time a new elem was created instead of querying the document tree during the updatePositions
--- added a calculation to determine how many background pizzas to create based on the size of the screen

- In the updatePositions methods, I made the following changes
--- moved the declaration of the phase variable outside of for loop
--- moved the scrolltop calculation outside of for loop into a seperate variable
--- access items array from local variable populated in the onload function instead of quering the document tree

- In the sytle.css, I updated the .mover class to include "backface-visibility: hidden" so the the entire page would not be repainted with every scroll

Resize pizzas optimizations
In order to get the pizza resize to take less than 2 ms, I made the following changesin main.js:
- In changeSliderLabel function, I replaced querySelector with getElementById
- In determineDx function, I replaced querySelector with getElementById
- In the changePizzaSizes, I made the following changes
--- Moved declaration of newwidth outside of for loop
--- Created a variable, randomPizzas, outside of the for loop, for the randomPizzaContainer and changed all references to use the variable instead of looking up in document tree
--- Replaced querySelector with getElementByClassName


