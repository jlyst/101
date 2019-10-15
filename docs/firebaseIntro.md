# A Firebase/Firestore Intro
This is a basic intro to using a Firestore database from the Firebase product family.

**Obectives**
- Create a Free Firestore Database
- Write and Read to the Database within a Web App (To-Do App)

## INSTRUCTIONS

### 1 - Login to Firebase
Login at https://firebase.com using Google Sign-In

### 2 - Create a Project
- Go to the console - button found in upper right-hand corner
- Create a new Project, naming it what you like (e.g. Firebase Intro)
- You can choose to disable analytics if you want.
- You may have to wait a few moments for the project to be built.

### 3 - Create a New Web App
- Select the Web App Icon Button `</>`
- Provide a Name and register the app (no need to add hosting)
- Stay on the page with the code samples. You will use this next.

### 4 - Set Up Your To Do App
In your functioning To-Do App (previous assignment) add the 

before `<script src="script.js"></script>`

```
<script src="https://www.gstatic.com/firebasejs/7.2.0/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/7.2.0/firebase-firestore.js"></script>
```

```
var db;
```

```js
  // Your web app's Firebase configuration
  var firebaseConfig = {
    apiKey: "***",
    authDomain: "***",
    databaseURL: "***",
    projectId: "***",
    storageBucket: "***",
    messagingSenderId: "***",
    appId: "***"
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);
 ```
 
 ```
 db = firebase.firestore();
 ```
 CLick the button to go to the console to continue.
 

### 5 - Create a Database (Firestore)
- Click the Cloud Firestore Option
- Click `create database`
- Select test mode
- Click next
- Use the default location
- Click done.

It will take a few moments to build. You can leave this web page open for now.

### 4 - To-Do App Edits

```
db.collection("log").add({
    action: "item added",
    time: new Date().toJSON()
  })
```
```
db.collection("log").add({
    action: "item deleted",
    time: new Date().toJSON()
  })
```

```
document.querySelector("#log").innerHTML = '<hr><div>TEST LOG</div>';
  db.collection("log").get().then(function (querySnapshot) {
    querySnapshot.forEach(function (doc) {
      document.querySelector("#log").innerHTML += `<div>${doc.data().action} at ${doc.data().time}</div>`;
    });
  });
```
