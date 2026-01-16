# MongoDB Vector Search Demo 

This guide shows how to demonstrate **Vector Search in MongoDB** using **MongoDB Atlas + Compass**.

## What You Will Build
- Create a MongoDB Atlas cluster
- Connect MongoDB Compass
- Store phone data with vector embeddings
- Create a Vector Search Index
- Run a semantic (meaning-based) search

---

## Step 1: Create a Free MongoDB Atlas Cluster
1. Sign up at MongoDB Atlas
2. Create a Free Tier (M0) cluster
3. Wait until the cluster is ready

---

## Step 2: Network Access
Allow access from anywhere (0.0.0.0/0).

---

## Step 3: Create Database User
Create a user with read/write permissions.

---

## Step 4: Connect Compass
Use the mongodb+srv connection string in MongoDB Compass.

---

## Step 5: Create Database and Collection
```
use shop
db.createCollection("products")
```

---

## Step 6: Insert Phone Data
```
db.products.insertMany([
  { name: "Pixel 7a", embedding: [0.20, 0.90, 0.40, 0.18] },
  { name: "iPhone SE", embedding: [0.19, 0.88, 0.39, 0.20] },
  { name: "Samsung Galaxy A54", embedding: [0.22, 0.85, 0.42, 0.21] },
  { name: "OnePlus Nord CE", embedding: [0.18, 0.82, 0.38, 0.19] },
  { name: "Redmi Note 12", embedding: [0.15, 0.80, 0.35, 0.17] },
  { name: "Galaxy S23", embedding: [0.40, 0.95, 0.60, 0.30] },
  { name: "iPhone 14 Pro", embedding: [0.45, 0.97, 0.65, 0.32] },
  { name: "Nothing Phone 1", embedding: [0.21, 0.83, 0.41, 0.20] },
  { name: "Motorola Edge 40", embedding: [0.17, 0.81, 0.37, 0.18] },
  { name: "Realme 11 Pro", embedding: [0.16, 0.79, 0.36, 0.16] }
])
```

---

## Step 7: Create Vector Search Index
```
{
  "fields": [
    {
      "type": "vector",
      "path": "embedding",
      "numDimensions": 4,
      "similarity": "cosine"
    }
  ]
}
```
Index name: vector_index

---

## Step 8: Run Vector Search Query
```
db.products.aggregate([
  {
    $vectorSearch: {
      index: "vector_index",
      queryVector: [0.20, 0.90, 0.40, 0.18],
      path: "embedding",
      numCandidates: 100,
      limit: 3
    }
  }
])
```

---

## Key Takeaways
- Vector Search works only in MongoDB Atlas
- Embeddings represent meaning as numbers
- MongoDB stores and searches vectors directly
