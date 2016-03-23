# Criterion C: Development
> List techniques used in app (ie. classes, methods, navigation stack, file handling, camera, database integration)

Both parts of the app, the frontend and the backend, are written in JavaScript with the ECMAScript 2015 specification.
I chose JavaScript because it is the language I have most experience working with and has one of the largest open-source communities.
I knew if I were to run into any problems, it wouldn't be too hard to find assistance online.

React Native by Facebook was chosen because it provides a bridge between JavaScript and native code (Objective-C, Swift and Java).
Being able to take advantage of iOS's and Android's native APIs would be necassary. React Native allowed me to do this without spending too much time digging into new languages.
React Native also provided high development efficiency – I could take an app written for iOS and then very easily translate it into an app for Android.

Node.js, Express and Mongoose were used to build the backend because, again, I had the most experience with the stack and the developer community was very open.


## Techniques Used

- Classes with inheritance
- Methods
- Promise chains
- Stacks (React Native's Navigator)
- Database
- Image handling and uploading
- Trees (React Native components and database relationships)
- Asynchronous Storage/local caching
- Graphic drawing (surfaces with paths)

## Classes

Classes are used throughout the product do build components and model routes.

Examples:

- `Avatar.jsx` – Extends the React Native `Component` class. It renders a circle image with specified `size` and `source` properties.
- `User.js` – Extends the Mongoose `Model` class. Contains static methods to create, read, update and delete user records form the database.

## Methods

Methods were used within the product to improve organization and reduce unneccasary repitition.
Since JavaScript executes code asynchronously, the use of Promise chaining is required to regulate code flow.

One example of a method would be `create()` inside of the `User` class. It creates new user objects and saves it to the database.

```js
static create(req: Object, res: Object): void {

  // Instantiate new model objects
  let user = new User(req.body.user);
  let followers = new Followers();

  // Define user -> followers association
  user.followers = followers._id;
  followers.user = user._id;

  // Persist the user record to database
  //
  // save method is inherited from the Mongoose Model class,
  // It returns a Promise object that provides method chaining
  // based on whether an event resolved or got rejected.
  user.save()

    // Persist followers record
    .then(() => followers.save())

    // Saving was successful; send user object response
    .then(() => res.json({ user }))

    // Saving failed; Send error to response
    .catch(err => res.send(err));
}

```

## Components

React Native provides a very specific paradigm of develepment. Everything within the app is a *component*, within a tree structure.
Every component has a list of properties and states. All data is sent downwards from components to child components and methods are sent upwards to mutate the state of parent components.
This pattern gives me direct control over how everything within the app is rendered onto the screen.
Components are only mounted when they are visible on the screen, not all at once when the app starts up; Re-rendering of components only happens when state is mutated – this process provides a highly efficient user interface.

A simple example of a component would be `GridOverlay`. It requires width, height and stroke properties from a parent component, then uses the Art library to draw a surface with a series of paths in a grid layout.

## Navigation Stack

React Native provides a `Navigator` API which is a stack of views. New views get pushed onto the top of the stack and popped out.
The push and pop methods get sent down the component tree, then the individual components send stack mutations up to the root component, which displays the view on screen.

## Open Source Software

Since there is so much going on in the app, I needed to take advantage of some open-source packages to help ease development
and make sure I wasn't re-inventing the wheel.

- Node.js – Server-side JavaScript environment.
- MongoDB – Cross-platform database.
- Flow – Allows static type checking in JavaScript, this allows me to write code that is easily maintainable.
- Babel – An ES6+ to ES5 transpiler; Allows me to integrate some of the latest and greatest features of JavaScript that aren't yet greatly supported. 
- Express – Used to handle all incoming and outgoing requests for the API.
- Multer – Handles multipart data; saves images onto the server.
- Mongoose – Provides a simple interface to MongoDB.
- Chalk – Colours any outputted logs in the server console.
- Nodemon – Used to run the development server; Listens for changes in code and restarts automatically.
- node-geocoder – Used to resolve coordinate data into readable city and country values.

### Frontend

- Art
- Flow
- React Native
- react-native-camera
- react-native-maps
- react-native-navbar
- react-native-scrollable-tab-view
- react-native-simple-store
- react-native-tab-navigator
- react-native-vector-icons

Word Count: 