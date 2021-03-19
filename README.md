# HTTP / AJAX II React Module Project: Movie CRUD

This module explored HTTP methods, REST interfaces, CRUD apps and using put and delete to allow editing and deleting functionality. We also dug into how to pass props to Route connected components and using URL params to get values from an api. In this project, you will practice each of these skills by implement various pieces of functionality in a movie database CRUD app.

## Objectives
- Understand how to use the post, put and delete HTTP methods to interact with server data.
- Understand how to sync server data with an applications internal state.
- Understand how to pass values into a Route component to allow for the updating of state.

## Introduction
CRUD applications are the foundation of most web applications. Being able to manage creating, edit and deleting data from an external source is as key a skill as it gets. In this project, you will complete the code nessisary to allow all of these fundmental actions.

![Movie DB Example](project-goals.gif)

***Make sure to complete your tasks one at a time and complete test each task before proceeding forward.***

## Instructions
### Task 1: Project Set Up
* [ ] Create a forked copy of this project.
* [ ] Clone your OWN version of the repository in your terminal
* [ ] cd into the project base directory `cd web-module-project-HTTP`
* [ ] Download server dependencies by running `npm install`
* [ ] Run the local web server by running `node server.js`
* [ ] Open a new terminal window and cd into the client code `cd client`
* [ ] Download project dependencies by running `npm install`
* [ ] Start up the app using `npm start`

### Task 2: Project Requirements
#### Editing a Movie
> *Let's start by walking through the process of adding the routing, component and service calls need for resource updating*

* [ ] First, we need to be able to navigate to the edit movie component. Add in the premade component used to edit a movie.

* [ ] Next, we need to be able to load in the current movie's attributes into our local form state. Add in the code needed to retrieve the movie data of the passed in id when the component mounts.

* [ ] At this point, nothing happens when the edit form is submitted. Add in the service call need to update the server with our updated movie when the edit form is submit button is clicked.

* [ ] Don't forget to make sure that your server data and your local state are in sync! Make any changes the edit route needed to modify global state within the edit form.

* [ ] Now that we have access to setMovies, made sure the updated list of movies is saved to our global state.

* [ ] Redirect the user to the currently edited movie's indivisual info page.

### Deleting a Movie
> *You added in a CRUD feature! Good job! Now let's get deleted squared away...*

* [ ] Identify the component that holds the "button" needed for deletion. Add an event hanlder to that button.

* [ ] Build your new event handler to make the request needed to delete the currentlt viewed movie. Observe what is returned from the request.

* [ ] You will once again need to keep the server and state data in sync. In the `App.js` class, complete complete the deleteMovie function so that it recieves a movie id and sets movies to be equal to all movies BUT the movie with the indicated id.

* [ ] Make the changes needed to give the correct component addes to your deleteMovie function.

* [ ] Call deleteMovie at the approprate time and redirect the user to the `/movies` route.

### Adding a Movie
> *Alright! You ready! Let's see you use the skills of the previous steps to build a crud function from start to finish.*

* [ ] Use `EditMovieForm.js` as a model to build an `AddMovieForm` component. The component should hold all the attributes of a new movie in local state as defined in the rest of application.

* [ ] Add in a route that allows access to the add Movie button.

* [ ] Locate the part of the ui that should navigate to your new AddMovieForm. Make that button redirect to your new component.

* [ ] On submission, run the approprate request for adding a movie with the component's state values.

* [ ] Make sure your component has access to and runs and modifications needed to global state and redirects to `/movies` after creation.

### Stretch goals
- Make the added DeleteMovieModal appear and be reacted to before deletion occurs.
- Add in add to favorites functionality. When the favorite button is pushed in the `Movie` component, make sure that when the favorite button is pushed, the id and name of the currently viewed into the favorite state slice in `App.js.`
- For extra credit, insure that only unique movies can be added as favorites. Consider the `.find` method for arrays.
- Style!

### Resource: API documentation 

#### GET `http://localhost:5000/api/movies`
- Retrieves all the Movies with the following formatting:
```
[{
  id: 5,
  title: 'Tombstone',
  director: 'George P. Cosmatos',
  metascore: 89,
  genre: "Drama",
  description: : "A successful lawman's plans to retire anonymously in Tombstone, Arizona are disrupted by the kind of outlaws he was famous for eliminating."
}]
```
#### GET `http://localhost:5000/api/movies`
- Retrieves all movies on the server.

#### GET `http://localhost:5000/api/movies/:id`
- Retrieves a movie with the passed value as id.

#### POST `http://localhost:5000/api/movies`
- Adds the movie passed in through body to the server movies list. Returns updated movies list.

#### PUT `http://localhost:5000/api/movies/:id`
- Replaced the movie with the passed in id with data passed in through body. Returns update movies list.

#### DELETE `http://localhost:5000/api/movies/:id`
- Removed movie with the passed in id. Returns the deleted movie's id.