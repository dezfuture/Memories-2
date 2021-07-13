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
* First to dispatch the action in the SearchPost we in actions/posts.js make a reducer **getPostsBySearch** in which we get searchQuery as a parameter and we fetch the searchQuery by **fetchPostsBySearch** and pass the searchQuery.
* Now for this reducer we have to create an endpoint in the index.js so we make that and pass the query in the path.
* Now in home.js in searchPost we dispatch the getPostBySearch function with **search and tags** as the parameters and as taga are an array so we use the **.join** to join the different array elements by ','.

> DIFFERECE BETWEEN qUERY AND PARAMS

- QUERY -> /posts?page=1
- PARAMS -> /posts/:id

#### SERVER:

- First in the routes we add the getPostBySearch route and now to manage this route we have to add the logic to the controllers folder we make the getPostBySearch controller.
- IN there we first take the title and then search in the posts by using those '$' operators firstly the title and then the tags which are an array so split those by ','.
- at last just to check in the action/posts.js{frontend} we destructure data two times.

* When we check we see that the search by name works but the search by tags is not working so fixing that.
* on seeing the code the mistake leading to this is that in Home.js in the searchPosts we are only looking for search term so we add **|| tags**.

#### CLIENT:

- When we search now we wanna see the posts related to that search or tag search so first in Home.js we first did history.push and then pushed the queried url.
- Then in the action/posts.js instead of console.logging the data we dispatch the action and gave it a new type **FETCH_BY_SEARCH** now also in the actiontypes.js we add this type and finally in the reducers we added the new case. Now we are able to search the posts related to that search.

* To handle this pagination effect first in our frontend we remove the useEffect from the Home.js and instead of that in the Pagination component pass the **page** as prop and then in the padination.jsx we destructure the page prop and use useEffect to dispatch the getPosts() function.
* Then in the action/posts.js we in the getPosts() action pass **page** as prop and then pass it to fetchPosts(**data**) now to send such req to the backend in the api/index.js we modify the fetchPosts() and also the path by giving it a dynamic string literal.

<!-- #### BACKEND:
* -->
