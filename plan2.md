### This is the continued version of our MERN application the memories project.

#### Initial dependencies which we are going to install are ->

#### CLIENT:

- @material-ui/lab: for bringing the effects of pagination and some other things
- @material-ui-chip-input: Input for the tags.

> Continuing with the client side.

- First in the components folder we created the **pagination.jsx** and over there imported pagination and paginationItem and then we in the functional component passes the self closing Pagination component in which we also pass some props and then pass **PaginationItem** component and also made the styles.js file for the **ul** styling and now to render this we in the Home.js render it after the form component and in a **Paper** component.

* First in the App component we imported **Redirect** and then we introduced some more routes and made on as PostDetails whose path is **/posts/:id** and just to check whether it's running correctly we just return a string.
* One more thing to focus over here is if someone manually goes to **/auth** then even when the user is signed in it takes user to the auth page which is not good so as we stored the users info. in localStorage we use it by JSON.parse and then in the auth route use ternary operator to render the pages or to redirect.
