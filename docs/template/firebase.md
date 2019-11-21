# Firebase Help

## Setting Up Your Firebase Account

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

### 4 - Set Up Your Web Application
In your web application make the following modifications.

**HTML**
Add the following code just before `<script src="script.js"></script>` in your HTML file.

```
<script src="https://www.gstatic.com/firebasejs/7.2.0/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/7.2.0/firebase-firestore.js"></script>
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

 Lastly, on the Firebase web site, click the button to go to the console to continue.
 
### 5 - Create a Database (Firestore)
- Click the Cloud Firestore Option
- Click `create database`
- Select test mode
- Click next
- Use the default location
- Click done.

It will take a few moments to build. You are now ready to use Firestore in your web app.

## Firebase Authentication to Allow User to Sign In (with Google account) to Your Web App

[Firebase Docs on Authentication](https://firebase.google.com/docs/auth/web/google-signin)

## Adding Data to Firestore

[Firebase Docs on Adding Data to Firestore](https://firebase.google.com/docs/firestore/manage-data/add-data)

## Deleting Data from Firestore

[Firebase Docs on Deleting Data from Firestore](https://firebase.google.com/docs/firestore/manage-data/delete-data)

## Reading Data from Firestore

[Firebase Docs on Reading Data from Firestore](https://firebase.google.com/docs/firestore/query-data/listen)


