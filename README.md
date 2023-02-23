# PokeAPI


## Description


This project was assigned at the end of the fifth week of General Assembly’s 3-month SEI (Software Engineering Immersive) course, in which I studied the fundamentals of software engineering with the aim to launch a career in this sector. The aim of the project was to show our ability at handling API's and manipulating the data we receive, we worked in pairs. I chose Pokemon.


## Deployment link:
Unfortunately, this is currently not deployed, due to a NPM error on my machine.


## Setup:
Clone the repo locally, then open in VS code, using:
‘code .’
Then: npm start


## Technologies Used:
- JavaScript, SASS and React.
- Bulma for styling.
- Development Tools: Visual Code Studio

## Brief:

The brief we received was to build an app that must fulfill the below requirement:
Consume a public API – this could be anything but it must make sense for your project.
Have several components - At least one classical and one functional.
The app can have a router - with several "pages", this is up to your discretion and if it makes sense for your project.
Include wireframes - that you designed before building the app.
Be deployed online and accessible to the public.

### Working team:
- Alice Lo (https://github.com/siuusunn)
- Jet Haze (https://github.com/CodebyJet/)

-----

## Planning:
The first day of the project, we spent planning it out, with a rough idea of what we wanted the end result to look like, what functions we thought it would need and how to implement them. We used excalidraw to plan the wireframe. We decided to pick the Pokemon API as we were both familiar with Pokemon, and from the choices available, we could make a clear picture of what our end goal would be. 

<img src="ReadMeAssets\readme-planning.png" >

We decided that Alice will create the page to show all the Pokemon, and I displayed the individual Pokemon when clicked on. We worked separately, but were available to help and bug fix for each other if needed. We worked over teams and updated each other with our progress as the project developed.

-----

### Individual Pokemon:
As I started, I focused on getting just one set Pokemon to appear, and then adapting the url to be changeable to all the Pokemon. To start, I just showed Bulbasaur (Not my original choice playing through the games - Team Squirtle!) as his PokeDex ID was number 1.

`
function PokedexIndividual() {
  const { id } = useParams();
  const [pokemon, setPokemon] = useState(null);
  useEffect(() => {
    getSinglePokemon(id)
      .then((res) => setPokemon(res.data))
      .catch((err) => console.error(err));
  }, [id]);

  if (pokemon === null) {
    return <p>Catching Pokemon...</p>;
  }
`

From this data, I wanted to show the name, picture of the Pokemon, where to find them and the PokeDex entry about them.

<img src="ReadMeAssets\bulbasaur.jpg" >

The data for the API was very nested, and not all the keys of the objects were in the right order, or in english. The habitat and PokeDex entry also weren't kept with the pictures and names of the Pokemon, so I had to pair them up. I created a function to find the first of each entry with an 'en' - English entry to display.

`
function CheckPokeDexDescription(pokeDex) {
  const descriptions = pokeDex.flavor_text_entries;
  const foundEnglish = descriptions.find(
    (element) => element.language.name === 'en'
  );
  return <p className="subtitle is-4" >{foundEnglish.flavor_text}</p>;
}
export default CheckPokeDexDescription;
`

After some testing to see if it all worked, I noticed some Pokemon don't have habitat or PokeDex entries (mostly they were just pikachu's in different hats or even special Pokemon). For these, I put that if if didn't have one of these, to show as 'Unknown' or 'this Pokemon hasn't been studied yet'

----

### Bonus Features:
The Search Bar. With the finished base MVP, I moved onto adding more functionality to the site. Alice wanted to add the ability to filter by type on the display of all Pokemon parts, and I wanted the ability to search for specific Pokemon.


<img src="ReadMeAssets\searchfunction.jpg" >


I found this actually fairly straight forward, I created a handleChange, that would navigate you to the specific Pokemon. However, this only really works if you know exactly how to spell the Pokemon, and as a dyslexic, I find it hard to spell every Pokemon, so I wanted an autocomplete - style feature, that would assist the user in navigating the site. Using a combination of map and match to find the Pokemon with the characters you are after, and slice to only display a certain number at a time (as there are over 1000 Pokemon, the list could get very long), I created a base autocomplete. I adapted this to be able to click on the filtered results, and this would also navigate the user to the desired Pokemon.


<img src="ReadMeAssets\searchbar-working.gif" >

With the styling added and fleshed out the site, the project was complete.


<img src="ReadMeAssets\Navbar-example.gif" >

----

## Wins?
The search bar was a huge win for me, when it all clicked on how to get it to work, that felt great. Also working with Alice was great, we both had a clear end goal in mind, with similar work ethics where we got things done and communicated our problems to work them out collaboratively.

----

## Bugs?
Currently, there is only two main bugs, it has trouble being deployed from my laptop. The other being the results list of the search bar doesn't clear after the input field is cleared.

Other than that bug, there's only the bug type Pokemon.

----

## Challenges?
The API we used itself was slightly challenging, the API was very messy in how it was constructed, sections would be in different places from Pokemon to Pokemon.

----

## Future Improvements:
In future iterations, I will come back to this and add the filter by type functionality, as I think it would be really neat.
