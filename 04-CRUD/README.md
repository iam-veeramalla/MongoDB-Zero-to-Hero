# CRUD

CRUD Operations in MongoDB

CRUD = Create, Read, Update, Delete

MongoDB CRUD feels easy because queries look like JSON.

👉 What you store is what you query.

### 🟢 CREATE (Insert Data)

Insert ONE document

```
db.users.insertOne({
  name: "Rahul",
  age: 22,
  skills: ["JavaScript", "MongoDB"],
  address: {
    city: "Delhi",
    country: "India"
  }
})
```

Insert MANY documents

```
db.users.insertMany([
  { name: "Anita", age: 24, skills: ["Python"] },
  { name: "Aman", age: 21, skills: ["Java", "Spring"] }
])
```

### 🟢 READ (Find Data)

Get all users

```
db.users.find()
```
Find by name

```
db.users.find({ name: "Rahul" })
```

👉 MongoDB matches key : value pairs.

Find using a nested field

```
db.users.find({ "address.city": "Delhi" })
```

### 🟢 UPDATE (Modify Data)

Update ONE document

```
db.users.updateOne(
  { name: "Rahul" },
  { $set: { age: 23 } }
)
```

Increment a number

```
db.users.updateOne(
  { name: "Rahul" },
  { $inc: { age: 1 } }
)
```

Push a value into an array

```
db.users.updateOne(
  { name: "Rahul" },
  { $push: { skills: "Node.js" } }
)
```

### 🟢 DELETE 

Delete ONE document

```
db.users.deleteOne({ name: "Aman" })
```

Delete MANY documents

```
db.users.deleteMany({ age: 21 })
```
