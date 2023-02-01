# ga-project-02

## Description

This project was assigned at the end of the fifth week of General Assembly’s 3-month SEI (Software Engineering Immersive) course, in which I am studying the fundamentals of software engineering with the aim to launch a career in this sector. The aim of the project was to show our ability at handling API's and manipulating the data we receive, we worked in pairs. I chose Pokemon.

## Deployment link:
Unfortunately, this is currently not deployed, due to a NPM error on my machine

## Technologies Used: 
To complete this project I employed JavaScript and React for the functionality.

## Brief:
With this project, we were given the brief to build a react application in two days, working in pairs. It had to be a public API, either one of a pre-selected group of API's or one that we found in our team. I picked Pokemon, as I found it to be the most engaging of the choices.

Our API had to: Show all the pokemon on one page, and show individual pokemon when clicked on, along with one other functionality.

## Planning:
The first day of the project, I spent planning it out, with a rough idea of what I wanted the end result to look like, what functions I thought I would need and how I may implement them. I used excalidraw to plan the wireframe of my game

<img src="ReadMeAssets\readme-planning.png" >

### Stage 1: 
Dividing the tasks. Alice created the page to show all the pokemon, and I displayed the individual pokemon when clicked on.

### Stage 2: 
As I started, I focused on getting just one set pokemon to appear, and then adapting the url to be changeable to all the pokemon. To start, I just showed Bulbasaur(Not my original choice playing through the games - Team Squirtle!) as his pokedex ID was number 1. 

<img src="ReadMeAssets\bulbasaur.jpg" >

### Stage 3: 
Of this data, I wanted to show, the name, picture of the pokemon, where to find them and the pokedex entry about them.

The data for the API was very nested, and not all the keys of the objects were in the right order, or in english. The habitat and pokedex entry also, weren't kept with the pictures and names of the pokemon, so I had to pair them up, I created a function to find the first of each entry with a 'en' - English entry to display.

### Stage 4: 
Integrating. Now that I could display Bulbasaur and all the data I wanted to show with them, it was time to merge the two halves and fix any merge disputes that may occur.

### Stage 5: 
Now, to be able to show all the pokemon when clicked on. For this I mostly just changed the URL that the data was set to pull, from Bulbasaur to a more dynamic base that went off the pokemon's ID.

### Stage 6: 
After some testing to see if it all worked, I noticed some Pokemon don't have habitat or pokedex entries (mostly they were just pikachu's in different hats or event special pokemon). For these, I put that if if didn't have one of these, to show as 'Unknown' or 'this pokemon hasn't been studied yet'

### Stage 7: 
The Search Bar. With the finished base MVP, I moved onto adding more functionality to the site. Alice wanted to add the ability to filter by type on the display all Pokemon part, and I wanted the ability to search for specific pokemon.

<img src="ReadMeAssets\searchfunction.jpg" >

### The Search bar: 
I found this actually fairly straight forward, I created a handleChange, that would navigate you to the specific pokemon. However, this only really works if you know exactly how to spell the pokemon, and as a dyslexic, I find it hard to spell every pokemon, so I wanted an autocomplete - style feature, that would assist the user in navigating the site. Using a combination of map and match to find the pokemon with the characters you are after, and slice to only display a certain number at a time (as there are over 1000 pokemon, the list could get very long), I created a base autocomplete. I adapted this to be able to click on the filtered results, and this would also navigate the user to the desired Pokemon.

<img src="ReadMeAssets\searchbar-working.gif" >

Unfortunately, I couldn't get it so the navbar stayed the same height and didn't extend down.

The filtered show all: We ran into some difficulties here. As the API was so large, it would only display the first 20 Pokemon, we adapted the url to have no filter, and hence show all the pokemon, this however, gave us back harder to use data. Mostly the pokemons name, and a url for the pokemon. Alice then tried to integrate the types I had set for them on the individual page a a key or value for them on the show all page. This proved hard than anticipated, and sadly didn't not make the deadline.

With the styling added and fleshed out the site, the project was complete.

<img src="ReadMeAssets\Navbar-example.gif" >

## Future Improvements:
In future iterations, I will come back to this and add the filter by types functionality, as I think it would be really neat.
