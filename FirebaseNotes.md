# Firebase Notes

## Storing Data
Firebase stores data in a json-like structure rather than a SQL database.

*Note:* Arrays are not allowed


## Commands

### Creating link to firebase
``` javascript
var config = {
  apiKey: "apiKey here",
  authDomain: "authDomain here",
  databaseURL: "db url here",
  storageBucket: "storage bucket url here",
  messagingSenderId: " sender id here"
};
firebase.initializeApp(config);
```
*Note:* Config variable generated from Firebase

### Reference to the databaseURL

#### `ref()`
Returns a Reference to the Query's location.

#### `firebase.database().ref()`
Returns the parent location of a Reference.
