

#### What is mongoose
- Mongoose is an Object Data Modeling (ODM) library for MongoDB and Node.js. It provides a straightforward, schema-based solution to model your application data. Mongoose helps you work with MongoDB collections by creating and managing documents in a more structured and organized way, ensuring validation, type casting, query building, and business logic hooks.

#### What is (ODM)
- ODM stands for **Object-Document Mapping**. It is a concept in software development that allows developers to interact with databases in an object-oriented way, particularly when working with **document-based databases** like **MongoDB**.

#### What ODM Does:

An ODM provides a bridge between the **documents** in a database and the **objects** in your programming language (such as JavaScript or Python). It allows you to work with data using objects instead of writing complex queries directly to the database.

---------
### How to use mongoose

- install mongo db in user system.
- install mongoose from npm.
- import mongoose from mongoose.
- connect mongoose in mongodb
```
mongoose.connect('mongodb://localhost:27017 /database_name').then(()=>{
	console.log("connnected to database")
}).catch((err)=>{
	console.log(err)
})

//27017 is default port check you mongodb.
//you can omit this port

```

#### create a schema
- it is like that a create a query with out value . that we use it as a template.
- create a new file user and do it.
```
import { mongoose } from 'mongoose'

const userSchema = new mongoose({

	username : {
		type : mongoos.Schema.Types.String;
		required : true;
		unque : true;
	}
})

export const user = mongoose.model("name your defined schema " ,your defined schema)

```
- mongoos.Schema.Types.String; , same exact method to give the data type of another type like int32 like that (it is a data type).
- if you want to use this schema you can import this scehma "user" from "user file"
```
const newuser = new user(body);
// body should be mached with the defined schema

const saveduser = await newuser.save()
//here we used await so , the functions should be in async.
//saveduser return the user details if user saved.
```

- to find the user from the db
```
const find = await User.findOne({ username })
//here we used await so , the functions should be in async.
```






