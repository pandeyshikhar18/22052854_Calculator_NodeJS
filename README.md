# MongoDB Guide

Welcome to the **MongoDB Guide** repository! This guide will help you set up MongoDB, understand basic commands, and integrate it with different programming languages.

## 🚀 Getting Started

### 📌 Installation

#### Install MongoDB on Windows, macOS, or Linux
- Download MongoDB from the [official website](https://www.mongodb.com/try/download/community)
- Follow the installation instructions based on your OS
- Verify installation:
  ```sh
  mongod --version
  ```

#### Run MongoDB
Start the MongoDB server:
```sh
mongod --dbpath /path/to/data/db
```

## 🛠 Basic Commands

### Start MongoDB Shell
```sh
mongosh
```

### Create a Database
```js
use myDatabase
```

### Insert Data
```js
db.users.insertOne({ name: "John Doe", age: 30, email: "john@example.com" })
```

### Find Data
```js
db.users.find()
```

### Update Data
```js
db.users.updateOne({ name: "John Doe" }, { $set: { age: 31 } })
```

### Delete Data
```js
db.users.deleteOne({ name: "John Doe" })
```

## 🔗 Integrating MongoDB with Python

Install the required package:
```sh
pip install pymongo
```

Connect and perform operations:
```python
from pymongo import MongoClient
client = MongoClient("mongodb://localhost:27017/")
db = client["myDatabase"]
db.users.insert_one({"name": "Alice", "age": 25})
print(list(db.users.find()))
```

## 🔗 Integrating MongoDB with Node.js

Install MongoDB package:
```sh
npm install mongodb
```

Connect and perform operations:
```js
const { MongoClient } = require("mongodb");
const client = new MongoClient("mongodb://localhost:27017");

async function run() {
    await client.connect();
    const db = client.db("myDatabase");
    await db.collection("users").insertOne({ name: "Bob", age: 28 });
    console.log(await db.collection("users").find().toArray());
    client.close();
}
run();
```

## 📄 License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🌟 Contributing
Feel free to submit a Pull Request if you'd like to improve this guide!
