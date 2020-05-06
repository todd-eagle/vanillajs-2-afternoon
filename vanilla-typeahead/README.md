# VanillaJS Typeahead

# Project Summary

The goal of this project is to build a typeahead similar to the Twitter Typeahead found <a href="https://twitter.github.io/typeahead.js/">here.</a> We'll cover how to access DOM nodes, how to make AJAX requests, and how to dynamically add HTML, all without using any additional libraries.

## Step 1

### Summary

To begin, we need data to search through. While there are many ways to interact with the data in a typeahead, we're going to load the data into the client and filter through it there using the fetch API.

### Instructions

* Open `./index.html`.
* Locate the opening and closing `script` tags.
* We'll write all of our JavaScript between these tags.
* Between the script tags, declare a variable called characters and set its value to an empty array.
* Using `fetch` make a request to the SWAPI API at `/api/people`s and store the resulting data in the people array.
  * Usage of the fetch API can be found <a href="https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch">here.</a>
  * Usage of the SWAPI API can be found <a href="https://www.swapi.co">here.</a>

### Solution

<details>

<summary> <code> ./index.html </code> </summary>

```js
const characters = [];

fetch('https://www.swapi.co/api/people')
    .then(response => response.json())
    .then(response => characters.push(...response.results))

```

</details>

## Step 2

### Summary

In this step, we'll make our data appear on the page. To dynamically add content to the view we need to target DOM nodes. DOM nodes are object representations of our HTML structure. There are several ways to access DOM Nodes including: `getElementById`, `getElementsByClassName`, `querySelector`, and `querySelectorAll`. You can find a summary of those methods <a href="https://www.digitalocean.com/community/tutorials/how-to-access-elements-in-the-dom">here.</a>

### Instructions

* Open `index.html`.
* Add another variable beneath our `characters` variable called `list` who's value is equal to the unordered list with an id of list in the `body` of our HTML.
  * We can now use this node as if it were a JavaScript object. This gives us access to all of its properties such as `innerHTML`, `event handlers`, `style`, etc.
  * Go ahead and `console.dir` our list variable to see the available properties in your browsers console.
* Now that we have access to the `ul`, let's render some `li` tags to show our character names.
  * Write a function called `render`.
  * In `render`, let's build some html.
    * Declare a variable called `html`.
    * Set `html` equal to the result of mapping over our characters array and returning a     


```

</details>

## Black Diamond

There are a few ways we can improve our typeahead.
  1. On page load the `list` is empty and shows just the border. Hide this and only show it when there is HTML to be rendered in the `list`.
  2. If there is no value in the input, set the `list` Node's display to `none`, and change it to `block` when a value is present.
  3. You should also clear the innerHTML of the list if the entry no longer matches a value from the characters array.
  4. Create a container that will hold `selected` elements. So that when you click on a name, it adds that name to another list.
  5. Once you can add the name, make it so you can only add the name once.

  A completed and fully functional version can be found on the solution branch.

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.
