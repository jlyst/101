# A Firebase/Firestore Intro
This is a basic intro to using a Firestore database from the Firebase product family.

**Obectives**
- Create a Free Firestore Database
- Write and Read to the Database within a Web App (To-Do App)

## INSTRUCTIONS

### 1 - Login to Firebase
Login at https://firebase.com using Google Sign-In

### 2 - Create a Project
- Go to the console. You can find the button found in the upper right-hand corner.
- Create a new Project, naming it what you like (e.g. Firebase Intro)
- You can choose to disable analytics if you want.
- You may have to wait a few moments for the project to be built.

### 3 - Create a New Web App
- Select the Web App Icon Button `</>` to create a new app.
- Provide a Name and register the app (no need to add hosting)
- Stay on the page with the code samples. You will use this next.

### 4 - Set Up Your To Do App
In your functioning To-Do App (previous assignment) make the following modifications.

**HTML**
Add the following code just before `<script src="script.js"></script>` in your HTML file.

```
<script src="https://www.gstatic.com/firebasejs/7.2.0/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/7.2.0/firebase-firestore.js"></script>
```

Add the following HTML element just below your results element--the one with `id="results"`. This is where database actions will be displayed as a log.
```
<div id="log"></div>
```

**JavaScript**
Add the following at the very top of your Javascript file. The global `db` variable will contain your Firestore database reference.
```
var db;
```

Copy the portion of code provided for you on the Firebase site that *looks* like the following. **IMPORTANT: You are not copying all of the code they provide you. Look carefully at the example below** Paste the code inside your `setup()` function at the top.

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
 
 Then add the following just below what you pasted.
 
 ```
 db = firebase.firestore();
 ```
 
 Add the following in your `submit()` function just after `updateStorage()` line;
 ```
db.collection("log").add({
    action: "item added",
    time: new Date().toJSON()
  })
```

Add the following in your `deleteItem()` function just after `updateStorage()` line;
```
db.collection("log").add({
    action: "item deleted",
    time: new Date().toJSON()
  })
```

Add the following inside your `render()` function at the end of the code block.

```
document.querySelector("#log").innerHTML = '<hr><div>TEST LOG</div>';
  db.collection("log").get().then(function (querySnapshot) {
    querySnapshot.forEach(function (doc) {
      document.querySelector("#log").innerHTML += `<div>${doc.data().action} at ${doc.data().time}</div>`;
    });
  });
```

 Lastly, on the Firebase web site, click the button to go to the console to continue.
 
### 5 - Create a Database (Firestore)
- Click the Cloud Firestore Option
- Click `create database`
- Select test mode
- Click next
- Use the default location
- Click done.

It will take a few moments to build. You can leave this web page open for now.

### 6 - Try Your To-Do App

If all is right, as you add and delete items you should see a basic log being updated at the bottom of your app. You will also notice the data is be shown on the firebase web site in the console view of your Firestore database.



