# Criterion C: Development
> List techniques used in app (ie. classes, methods, navigation stack, file handling, camera, database integration)

Both parts of the app, the frontend and the backend, are written in JavaScript with the ECMAScript 2015 specification.
I chose JavaScript because it is the language I have most experience working with and has one of the largest open-source communities.
I knew if I were to run into any problems, it wouldn't be to hard to find assistance online.

Tools like React Native were chosen because it provides a bridge between JavaScript and native code (Objective-C, Swift and Java).
Being able to take advantage of iOS's and Android's native APIs would be necassary. React Native allowed me to do this without spending too much time digging into new languages.
React Native provided high development efficiency – I could take an app written for iOS and then very easily translate it into an app for Android.

Node.js, Express and Mongoose were used to build the backend because, again, I had the most experience with the stack and the developer community was very open.

## Classes
> Describe how and why classes were used in the app
  and what differs from frontend differs from backend (ie. React components, Mongoose routes).
  Rundown each class, what they accomplish.

## Methods
> How methods were used to accomplish goals.
  Go through some example methods in code.

## Components

React Native provides a very specific paradigm of develepment. Everything within the app is a *component*, within a tree structure.
Every component has a list of properties and states. All data is sent downwards from components to child components and methods are sent upwards to mutate the state of parent components.
This pattern gives me direct control over how everything within the app is rendered onto the screen.
Components are only mounted when they are visible on the screen, not all at once when the app starts up; Re-rendering of components only happens when state is mutated – this process provides a highly efficient user interface.

The product uses 18 custom components and 16 views. Some examples of components would be `SpotCard` or `Avatar`, views would be `Camera` or `Profile`. Every view is made up of components and every component is made up sub-components.

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