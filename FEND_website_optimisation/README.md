## Website Performance Optimization portfolio project

###Part 1: Optimize PageSpeed Insights score for index.html

How to run:

1. Go to the "dist" folder
2. Double click on "index.html" or open it in a browser

How the build tools were used:

1. Go to the "src" folder
2. Open a Terminal window and type 

	```bash
  	$> cd /src
	$> npm run build
	```

  This will build the assets for part 1 of the project - "PageSpeed Score".

####Outline of optimisation methods:

1. Used the "async" attribute for the google script tag.
2. Used npm build tools for minification and inlining css.
3. Made images responsive by using the "srcset" attribute in the img tag.

###Part 2: Optimize Frames per Second in pizza.html

How to run:
	1. Method 1: Go to /dist/views and open "pizza.html" in a browser. 
  	2. Method 2: Click on the "Cam's Pizzeria" link in /dist/index.html. 

####Outline of optimisation methods:

1. Prevented forced synchronous layout by reading style first and then batch style changes. This method was used in several places including the resizePizzas function
2. Reduced the number of .mover elements from 200 to 32 
3. Used requestAnimationFrame for all animation changes on screen
4. Debounced input handler for scroll in "window.addEventListener('scroll', onScroll);" and stored the scrollY value to be read only once during requestAnimationFrame
5. Put the .mover element in a separate layer by using the css property "will-change: transform;"
6. Created a "var moversLeftArray = []" to store the initial basicLeft value of all the mover elements so that there is no need to do a layout read during scroll since the left position can be referenced from its initial value upon page load. So only a style change is needed to write the new left position values.
