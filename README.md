# Disney Characters

This was our second project on the coding bootcamp and it is a Disney characters database where users can find the characters and see what tv shows, films or video games they were in.

## Timeframe

This was a pair project with my colleague Joana and we were given 2 days to create a React application using the Disney API.

## Technologies Used 💡

- HTML
- Saas
- JavaScript
- React
- Insomnia

## Brief
- Consume a public API – this could be anything but it must make sense for your project.
- Have multiple components.
- The app can have a router - with several "pages", this is up to you and if it makes sense for your project.
- Include wireframes - that you designed before building the app.
- Be deployed online and accessible to the public.

## Planning


Regarding our teamwork strategy, we kicked off by jointly tackling different segments of the project. As we progressed, we allocated responsibilities in line with our individual strengths and interests. I assumed the role of writing the functionality for our project and Joana focused on the styling/design elements.

### Wireframe

Firstly, we selected the Disney API, created a wireframe on Figma and designed a colour scheme. Then we collected gifs and images that we wanted to include in our web application. We created three pages, a homepage, a secondary page to display all of the characters and a third page to display a single character with their information from the API. 

![Wireframe](/public/images/wireframe.png)


### Build Process

### The Disney API

The data we wanted to get from the Disney API was, the character name, image url, films, tv shows and video games. However, the format of the data was difficult to work with and it returned non-normalized data, such as titles and images that had to be cleaned on the client side.

![API](/public/images/insomnia.png)

The `CharactersList` component's state management was critical. It needed to handle asynchronous API calls while providing feedback to the user. By using an async function inside the useEffect hook, I made sure that the character data is fetched and set into state as soon as the component mounts. The empty dependency array `[ ]\` ensures that this effect runs once upon mount.

![characterlist](/public/images/character-list.png)

### Dynamic rendering

Once the data is fetched, rendering the list of characters dynamically was next. To ensure performance and key management, I used the character IDs (`character._id`) as keys for the list items, since they are unique.

![characters-map](/public/images/characters-map.png)

Throughout the development process, my focus was on writing clean, efficient, and reusable code. Ensuring data consistency, handling edge cases, and maintaining a smooth user experience were my top priorities. 

### Challenges

Some of the disney characters in the API had placeholder images, however some didn’t so therefore we had to add our own placeholder image too. 

Another issue with the API was that it had an internal server error and was fragile so halfway through the project it would stop and start working again. I would’ve saved the data in a `.json` file so that if the API returned a response of a 500 status code, then the application would read from a cached `.json` file.

### Wins

In this code snippet, I implemented a ternary operator to check if the length of the array for that category is greater than 0 (indicating that there are items to display).
`If true (length > 0)`, it maps over the array and renders each item.
`If false (no items)`, it renders a `<div>` with a message indicating that there are no items found for that category.

![ternary-operator](/public/images/ternary-operator.png)

### Key Learnings

- I feel more confident with using React and fetching data from an external API.
- Pair programming definitely taught me how to read and understand other people’s code.
- I gained valuable understanding of the significance of cooperative engagement in a group setting, valuing the perspectives of each other, and offering support when needed. This exposure enhanced my abilities to interact effectively with others and contributed to a more cohesive team environment.


### Future Improvements

- Add pagination and a search bar.
- Make it responsive.
