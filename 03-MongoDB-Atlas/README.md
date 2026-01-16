# MongoDB Atlas & Compass 

This guide explains:
- What MongoDB Atlas is
- How to create a FREE cluster
- How to connect using MongoDB Compass (GUI)

---

## What is MongoDB Atlas?

MongoDB Atlas is MongoDB’s fully managed cloud database.

You don’t need to:
- Install MongoDB
- Manage servers
- Handle backups or scaling

Atlas does everything for you.

---

## Step 1: Create a MongoDB Atlas Account

1. Go to [Atlas](https://fandf.co/4sxY6rQ)  
2. Click **Sign Up**
3. Sign up using Google, GitHub, or Email

After login, you’ll see the Atlas Dashboard.

---

## Step 2: Create a FREE Cluster (M0)

1. Click **Create**
2. Choose **Shared Cluster**
3. Select **M0 (FREE)**
4. Choose:
   - Cloud Provider: AWS (default is fine)
   - Region: closest to you
5. Click **Create Cluster**

Cluster creation takes 1–3 minutes.

---

## Step 3: Create a Database User

1. Go to **Database Access**
2. Click **Add New Database User**
3. Set:
   - Username
   - Password
4. Role:
   - Read and write to any database
5. Click **Add User**

Save the username and password.

---

## Step 4: Allow Network Access (IP Whitelist)

1. Go to **Network Access**
2. Click **Add IP Address**
3. Choose **Allow Access from Anywhere**
4. Click **Confirm**

(Only for learning purposes)

---

## Step 5: Install MongoDB Compass

MongoDB Compass is a GUI tool to view data visually.

1. Download from:
   https://www.mongodb.com/try/download/compass
2. Install and open Compass

---

## Step 6: Get Connection String

1. In Atlas, click **Connect**
2. Choose **Connect using MongoDB Compass**
3. Copy the connection string

Example:
```
mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/
```

Replace username and password.

---

## Step 7: Connect Using MongoDB Compass

1. Open MongoDB Compass
2. Paste the connection string
3. Click **Connect**

You are now connected to MongoDB Atlas.

---

## Step 8: Create Database & Collection

1. Click **Create Database**
2. Database Name: myFirstDB
3. Collection Name: users
4. Click **Create**

---

## Step 9: Insert First Document

1. Open users collection
2. Click **Add Data → Insert Document**
3. Paste:

{
  "name": "Alice",
  "age": 25,
  "email": "alice@example.com"
}

4. Click **Insert**

---

## What You Learned

- Created a free MongoDB Atlas cluster
- Connected using MongoDB Compass
- Inserted your first document

---

Happy Learning MongoDB 💚
