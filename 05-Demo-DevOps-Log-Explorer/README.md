# DevOps Logs Explorer with MongoDB

What This App Does ?

- Simulates a running service
- Generates random logs every few seconds
- Pushes them into MongoDB
- Feels like real-time application logging

### Step 1: Install Dependency

`pip install pymongo`

We use PyMongo, MongoDB’s official Python driver.

### Step 2: Dummy Python Log Producer App

```
import time
import random
from datetime import datetime
from pymongo import MongoClient

# 1. Connect to MongoDB
client = MongoClient("mongodb://localhost:27017")
db = client["devops_logs"]
logs_collection = db["logs"]

services = ["auth-service", "payment-service", "order-service"]
levels = ["INFO", "WARN", "ERROR"]

# 2. Keep generating logs
while True:
    log = {
        "service": random.choice(services),
        "level": random.choice(levels),
        "message": "Dummy log message",
        "timestamp": datetime.utcnow(),
        "host": f"server-{random.randint(1,3)}"
    }

    logs_collection.insert_one(log)
    print("Inserted log:", log)

    time.sleep(2)  # wait 2 seconds
```

### Step 3: Run the App

`python log_producer.py`

You’ll see logs printing continuously:

Inserted log: {'service': 'auth-service', 'level': 'ERROR', ...}

### Step 4: View Logs Live in MongoDB Compass

Open MongoDB Compass

Go to devops_logs → logs

Click Refresh

Watch logs appear in real time 🔥

```
🔍 Example Queries (Try While App Is Running)
db.logs.find({ level: "ERROR" })

db.logs.find({ service: "payment-service" })

db.logs.find().sort({ timestamp: -1 })
```
