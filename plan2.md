### This is the continued version of our MERN application the memories project.

#### Initial dependencies which we are going to install are ->

#### CLIENT:

- @material-ui/lab: for bringing the effects of pagination and some other things
- @material-ui-chip-input: Input for the tags.

> Continuing with the client side.

- First in the components folder we created the **pagination.jsx** and over there imported pagination and paginationItem and then we in the functional component passes the self closing Pagination component in which we also pass some props and then pass **PaginationItem** component and also made the styles.js file for the **ul** styling and now to render this we in the Home.js render it after the form component and in a **Paper** component.

* First in the App component we imported **Redirect** and then we introduced some more routes and made on as PostDetails whose path is **/posts/:id** and just to check whether it's running correctly we just return a string.
* One more thing to focus over here is if someone manually goes to **/auth** then even when the user is signed in it takes user to the auth page which is not good so as we stored the users info. in localStorage we use it by JSON.parse and then in the auth route use ternary operator to render the pages or to redirect.
* In Home.js now we import more material ui components like appBar etc.. and then also made the styles.js now we use over here on feature of **react-router-dom** and there we make a function useQuery in which it stores the searchPage and the searchTerm and now we make all other hooks and use them.
* Now for managing the value in the text field we use useState
* The **ChipInput** imported add that tag search style to the tag search field.
* We add the ChipInput in the AppBar component and pass the props required and then also we make a button and pass the onClick prop.
* > In the ChipInput component
  - use state to get the value of the tag entered.
  - make the add and delete handler.
* we also introduced the **handleKeypress** to trigger search even when **Enter** is pressed.
* In the Button we add the searchPost to search the post.
