## Website Performance Optimization portfolio project

## Summary

This project is about improving the performance of loading and rendering an existing given portfolio site. We can measure the speed of this site using chrome dev tools and perform optimisations required to improve page speed. The page speeds insights score cann be seen using google page insights.

## Steps to launch:

1. Clone the repo to your local machine
2. Launch a local http server to test.Open a terminal window, navigate to the directory of the project, and run a python command:
          `python -m SimpleHTTPServer 8080`
3. Open a browser and visit localhost:8080
4. Download and install [ngrok](https://ngrok.com/) to the top-level of your project directory to make your local server accessible remotely.
5. In the same directory, run the commend: `ngrok http 8080` to access a secure public URL to the site.
6. Copy the public URL given by nrok from the terminal window and paste it into your browser to view the site.
7. Use Google PageSpeed Insights to check the Google PageSeed score of the homepage

## changes in views/js/main.js to improve pizza.html

1. Modfied the changePizzaSizes function :changed the element selection by using class name rather than querySelectorAll. added the elements to an array of pizzaElements.
2. Moved the computation of the dx and newwidth variables outside of the for loop as it doesn't seem necesary to recompute them on each pass through that loop.
3. Modified the updatePositions function: changed the  mover element selection by using class name rather than querySelectorAll
4. Since there are only 5 unique phases of the moving pizzas, I moved the phase calculation into its own for loop that appends each phase to an array called phaseList, rather than declaring and setting the phase variable each time.
5. The pizza item styles are changed by accessing the relevant element of the phaseList array as it loops through each element in the items array.
6. Moved the declaration of the pizzaDivs variable outside of the for loop, since it is only necessary to make one DOM call there.
7. Changed the number of pizzas generated on page load to be based on the browser window resolution.
8. Changed the querySelector call for selecting movingPizzas1 element to getElementById, saved it to a local variable called movingPizzas, moved it outside of the for loop, and referenced the movingPizzas variable inside the loop.

## Optimizations to views/css/style.css

1. Added backface-visibility: hidden; to the .mover class, to move each animated pizza to its own composite layer.

## Optimizations to index.html

1. Inlined the styles.css to avoid render blocking.
2. minified the css and javascript files using grunt.
3. optimized the images to reduce the page load time.
4. used `aync` for javascript to avoid render blocking.
5. minified the html file using grunt to improve page score.

