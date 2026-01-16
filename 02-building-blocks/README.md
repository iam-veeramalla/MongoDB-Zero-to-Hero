# 🧱 MongoDB Building Blocks 

This guide explains the **core building blocks of MongoDB** in the simplest possible way.
You can directly use this file as a **GitHub README.md**.

---

## What is MongoDB?

MongoDB is a **NoSQL (Non-Relational) database** that stores data in a **JSON-like format**.
It is flexible, easy to read, and ideal for modern applications.

---

## Visual Overview

Think of MongoDB like **folders and files**, but designed for data.

MongoDB  
└── Database  
  └── Collection  
    └── Document  
      └── Fields  

---

## 1. Database

- Top-level container
- Holds multiple collections
- Similar to a database in SQL

Example:
```
ecommerce_db
```

---

## 2. Collection

- Group of related data
- Similar to a table in SQL
- No fixed columns

Example:
```
users
orders
products
```

---

## 3. Document (Most Important)

- A single record
- Stored in JSON-like format
- Each document can have different fields

Example:
```json
{
  "_id": 1,
  "name": "Amit",
  "email": "amit@gmail.com",
  "age": 25
}
```

No NULL values required.
Store only what you need.

---

## 4. Field

- Key-value pair inside a document
- Similar to a column in SQL

Example:
```json
"name": "Amit"
"age": 25
```

---

## 5. _id Field

- Unique identifier for every document
- Automatically generated
- Automatically indexed

Example:
```json
"_id": ObjectId("65a1f9c2e8a...")
```

---

## 6. JSON vs BSON

- You write JSON
- MongoDB stores BSON

BSON is faster and supports more data types.

---

## 7. Index

- Improves query performance
- _id index exists by default

Example:
```js
db.users.createIndex({ email: 1 })
```

---

## Why MongoDB is Beginner Friendly

- No rigid schema
- JSON-like syntax
- Easy to scale
- Matches real-world data

---

## What to Learn Next

- CRUD operations
- MongoDB Compass
- Schema Validation
- Indexing
