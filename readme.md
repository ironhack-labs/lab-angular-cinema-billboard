![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# DE | Cinema Billboard

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_3b41840a621af4b092e9a85c32baf612.png)

## Learning Goals

After this lesson, you will be able to:

- Create an angular service to share information with all the components in your application.
- Create angular routes with parameters.
- Create different components related between them.

## Requirements

- [Fork this repo](https://guides.github.com/activities/forking/)
- Clone your fork into your `~/code/labs` folder.

## Submission

Upon completion, run the following commands:

```bash
$ git add .
$ git commit -m"done"
$ git push origin master
```

Navigate to your repo and create a Pull Request -from your master branch to the original repository master branch.

In the Pull Request name, add your campus, name, and last name separated by a dash "-".

## Deliverables

All the files of your project, including the service and the different components you will use to create your solution.

## Introduction

Nowadays, cinemas are not one of the best business to run. The Internet is damaging the industry, giving the chance to find any movie without having to pay to watch it. A Cinema has contacted Ironhack to help them changing the vision that people have.

Their idea is to redo their website by using Angular2. They think that if they use the latest technologies on their website, people will see them with another point of view, and their popularity will grow up importantly.

The cinema has 5 different rooms, where you will be able to watch 5 movies. The newset purposal of this cinema is that they are not going to show you the lastest movies, but your favorite ones! So you will have to help them deciding what to show on the rooms.

### Iteration 1: Service Creation

First of all, we are going to create an Angular Service to handle all the movies information. This services is going to have the following:

**`Movies`**

It will be an Array of objects, that will contain one item per each cinema room. Each object inside the array will have the following information:

- An `id`, that will be a unique number used to distinguish between movies.
- A `title`, that will be an string, containing the movie title.
- A `poster`, that will be an string and will contain a URL to an image that represents the movie.
- A `synopsis`, that will contain a brief description about the movie. It has to be an string.
- `Genres` will be an array of strings, where we will indicate which genres represent the movie.
- The `year` of the movie, that will be a number.
- An string where we will indicate the `director` of the movie.
- An array with all the `actors` names, using one string per each actor.
- Another array of strings where we will indicate the `hours` that the movie is projecte. i.e. `Wednesday 19:30, 22:30` would be an element of this array to indicate that you can watch a movie on wednesday at 19:30h and 22:30h.
- Last, but not least, the `room` number where people can watch the movie.

In the `Movies` array you will have to create an element for each movie, and fill up the different fields we just defined. **Use your favorite movies to do that**.

**Methods**

The service will also have two different methods that will be used later on the project. The methods you have to create are the following:

- `getmovies()` that will return the array of movies.
- `getMovie(id)`, that will receive as a parameter a movie number id, and will return the indicated movie.

**Tasks**

- Create a `Cinema` service.
- Add a `Movies` array of objects. Each object will have the following properties:
  - `id`, number.
  - `title`, string.
  - `poster`, string.
  - `synopsis`, string.
  - `genres`, array of strings.
  - `year`, number.
  - `director`, string.
  - `actors`, array of strings.
  - `hours`, array of strings.
  - `room`, number.
- Add a `getMovies()` method, that will return the array of movies.
- Add a `getMovie(id)` method, that receives a number id as a parameter and returns an object from the `Movies` array.

### Iteration 2: Routes

In the second iteration of this exercise, we will create two different routes to show the information of our cinema. In the main page of the application, we will show a list with all the movies in the cinema. Once you click in one of the movies, you will see all the information of a movie.

First of all, we have to install `@angular/router` in the project, and create the components we will use to show the information: `MyHomeComponent` and `MyMovieComponent`. Once we have created all the components we need, we have to create two different routes:

- `/home`, that will render the `MyHomeComponent` component.
- `/movie/:ud`, that will render the `MyMovieComponent` component.

We will not create the logic of each component yet, but we have to add the `<router-outlet></router-outlet>` tag in the `app.component.html` file to be able to load the different information depending on the indicated route.

**Tasks**

- Add the `@angular/router` to the project.
- Create two components:
  - `MyHomeComponent`
  - `MyMovieComponent`
- Create the different routes to show each component:
  - `/home`, to show `MyHomeComponent`
  - `/movie/:id`, to show `MyMovieComponent`
- Add `<router-outlet></router-outlet>` tag to `app.component.html` file

### Iteration 3: Home Page

We are going to work over the `MyHomeComponent` component we created in the iteration above. We have to use the `Cinema` provider to load all the movies information we have declared in the array.

We have to show in the main page the list of movies that are available in the Cinema. Each movie has to be a link to the movie page.

Remember that the goal is to convert as many visitors as possible in our clients. Style a little bit the page to show the information.

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_9e7df057fd85adf216cc180a05f9b3db.png)

**Tasks**

- Load all the movies from the `Cinema` service, with the `getMovies()` method defined on it.
- Show the information in the `/home` page.
- Create a link for each movie that redirects the user to `/movie/:id`.
- Style the page.

### Iteration 4: Movie Page

Once the user visits a movie page, we have to show them the information. Again, we need to use the `Cinema` service to load the information of the movie. We have to show all the movie information, and add a "Go back" button to let the user go back to the home page.

Remember to style the page to show all the information of the movie.

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_2ecbb29232615506fcddd875d450582e.png)

**Tasks**

- Load the movie from the `Cinema` service, with the `getMovie()` method defined on it. Use the `:id` parameter in the URL to get the correct movie.
- Show all the data of the movie in the view.
- Add a "Go back" button, that redirects the users to the home page.
- Style the page.

/Happy coding!
