**DAY-1:**


Github basic commands:

1.To create a new branch:
>>git checkout -b branchname

2.To open an existing branch
>>git chechout branchname

3.To merge any two branches
 -> Always open man branch
  >>git merge branchname(conflicts arises if 2 branches have same filename with different content)


**DAY-2**


# 📌 Notes: MongoDB Atlas Setup & Mongo Shell Usage

## 1. Create MongoDB on Cloud (Atlas)

1. Go to 👉 [https://www.mongodb.com/atlas](https://www.mongodb.com/atlas).
2. Sign in with Google/GitHub or create a free account.
3. Click **Build a Database** → choose **Free Cluster (M0)**.
4. Choose:

   * **Cloud provider** (AWS, Azure, or GCP).
   * **Region** (nearest to your location).
   * Click **Create Cluster**.
   * Cluster takes \~2–3 mins to deploy.

---

## 2. Install Mongo Shell on Windows

1. Download **MongoDB Shell (mongosh)** 👉 [MongoDB Download Center](https://www.mongodb.com/try/download/shell).
2. Install and add it to **PATH** (during installation, check "Install MongoSH").
3. Verify installation:

   ```sh
   mongosh --version
   ```

   If it shows version → installation successful.

---

## 3. Setup MongoDB Atlas Network Access

1. In **Atlas Dashboard** → Left menu → **Network Access**.
2. Click **Add IP Address**.
3. Options:

   * **Current IP Address** → allows only your PC.
   * **0.0.0.0/0** → allows **all IPs** (useful for development).

     * ⚠️ Not recommended for production (security risk).
4. Save changes.

---

## 4. Create / Update MongoDB User

1. Go to **Atlas Dashboard** → Left menu → **Database Access**.
2. Click **Add Database User**:

   * **Username**: e.g., `aishuks`
   * **Password**: e.g., `Aira123`
   * Role: Choose `Atlas Admin` or at least `Read and write to any database`.
3. Click **Add User**.

👉 For backend simplicity (without URI encoding issues):

* Avoid special characters in username/password (`@`, `#`, `!` etc.).
* Example:

  * **Username**: `aishuks`
  * **Password**: `Aira123`
* This way, you don’t need URL encoding in the connection string.

---

## 5. Connect Mongo Shell to Atlas

1. Go to **Clusters → Connect → Connect with Mongo Shell**.
2. Copy connection string:

   ```sh
   mongosh "mongodb+srv://cluster0.xxxxx.mongodb.net/" --username myuser
   ```
3. Enter password when prompted.
4. Now you’re inside the **Mongo Shell** connected to Atlas.

---

## 6. Basic Mongo Shell Commands

Once connected:

```sh
# Show all databases
show dbs

# Switch to (or create) a database
use students_db

# Create a collection and insert data
db.students.insertOne({ name: "Alice", age: 21 })

# View all collections
show collections

# Fetch data
db.students.find()

# Update data
db.students.updateOne({ name: "Alice" }, { $set: { age: 22 } })

# Delete data
db.students.deleteOne({ name: "Alice" })
```

---

## 7. Update Settings Later

* **Change Network Access**:
  Atlas → **Network Access** → Edit or Delete IP Whitelist.
* **Change Username/Password**:
  Atlas → **Database Access** → Edit User.

---

✅ Now you can:

* Create MongoDB cluster on **Atlas**
* Connect with **Mongo Shell on Windows**
* Manage **IP access** & **Users/Passwords**
* Run queries directly from **mongosh**

---

## 🔹 8. Using the Atlas Web UI

1. Log in to [MongoDB Atlas](https://cloud.mongodb.com/).
2. Go to **Database → Clusters → Browse Collections**.
3. Select your cluster and then select the database you created.
4. You’ll see:

   * All **collections** (like SQL tables).
   * Documents inside each collection.
   * You can also **filter, insert, edit, delete** documents right there.

---

## 🔹 9. Using Mongo Shell (`mongosh`)

If you are already connected with:

```sh
mongosh "mongodb+srv://cluster0.xxxxx.mongodb.net/" --username myuser
```

Then:

```sh
# list all databases
show dbs  

# switch to your database (example: testdb)
use ecom_app_learn_db 

# list all collections in the current database
show collections  

# view documents from a collection (example: students)
db.products.find()
```

---

✅ **Quick Tip:**

* Collections in MongoDB = Tables in SQL.
* Databases hold multiple collections.
* You must `use <dbname>` before `show collections`, otherwise it will show collections of the current DB (default = `test`).





TO IMPROT DATA INTO THE BACKEND/ATLAS:

* Download mongodb database tools
* Environmental variables>>path>>new>>paste -> path of mongodb tools till u get last folder
* Download the required data file(i.e products.csv)
* open windows powershell>>
   -> run >> mongoimport --version(to check if its there or not)
* run the command  mongoimport --uri "mongodb+srv://aishuks:Aira123@cluster0.wpjrhxr.mongodb.net/gamingclub" --collection products --type csv --headerline --file "C:\Users\aishu\OneDrive\Desktop\products (4).csv"
* it'll successfully reflect in the atlas.








**DAY-3**






SPRINGBOOT:

* Install spring initializer
   ->config(project:Maven , Language: Java , springboot:3.5.5)
  ->Added dependencies,spring web,spring data mongodb
* Import it to eclipse IDE/ VS Code
* start the backend code
 ->create Products.java
 ->ProductsController.java
 ->ProductsRepository.java

* Modify applicationproperties
* Run gamingsystemapplication.
* apply HTTP operations in postman




