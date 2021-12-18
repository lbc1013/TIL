## How To connect db using mongoDB

// 1. Create connection

````javascript
const mongoose = require("mongoose");

//Connect database called DB_NAME.
mongoose.connect('mongodb://localhost/DB_NAME')
  .then ((result) => {
    console.log('connected to db');
  })
  .catch((err) => {
    console.log('not connected to db');
  })
````

// 2. Create Schema.

````javascript
const { Schema } = mongoose;

//Schema setup example
const groceryListSchema = new mongoose.Schema({
  item: {
    type: String,
    unique: true
  },
  quantity : {
    type: Number
  }
});
````

// 3. Create Model

````javascript
const GroceryList = mongoose.model('GroceryList', groceryListSchema);
````

// 4. Create an instance of a model (document)

````javascript
  const groceryItem = new GroceryList({
    item: userItem,
    quantity: userQuantity
  });
````

// 5. Save the document in the database.

````javascript
groceryItem.save()
  .then(() => {

  })
  .catch((err) => {
    console.log('There is an err', err);
  })

````