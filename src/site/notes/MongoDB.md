---
{"dg-publish":true,"permalink":"/MongoDB/","tags":["coding"]}
---


---
# MongoDB
> A [[Database Management Systems (DBMS)\|DBMS]] which uses a slightly different terminology than [[SQL\|SQL]], [[MySQL\|MySQL]] and [[PostgreSQL\|PostgreSQL]].

> [!note] Note: Nomenclature Changes
> MongoDB uses the words "Collections" instead of Tables and the term "Documents" instead of Rows. 

MongoDB allows for a fewer relations, data to be stored together in one large collection and querying to be faster since less number of collections are to be navigated.

### Documents
Documents are MongoDB's equivalent of Rows in a Database Table
Documents are saved in JSON format.

JSON Format is preferred for many reasons but primarily for its ability to allow [[MongoDB#Embedded Documents\|Embedded Documents]] since a JSON object can contain an attribute which itself is another object. 

Schema does not need to be changed when a specific row is different from the others in case of using MongoDB since each row in an SQL table is a document and if a new document has a few less/extra fields, only said document needs to be changed. 

This allows MongoDB to have broader and fewer collections, making queries faster and much better.

Each Document can be a maximum of 16 MB and can have 100 levels of nesting.

### MongoDB Compass UI
MongoDB Compass is a [[Graphical User Interface (GUI)\|Graphical User Interface (GUI)]] that people can use to navigate MongoDB's options. Other option is to use MongoDB [[Command Line Interface (CLI)\|Command Line Interface (CLI)]].

### Installation
Search "MongoDB download" and download it from the official website.
When installing, check the option to install MongoDB as a service.

After the installation, please also go ahead with installing the MongoDB shell if you wish to use that instead.

>[!quote] Sarcasm
>"Real Devs always use Command Line!"
>~ some CLI enjoyer, probably

### Basic Commands
- Show Existing Databases: `show dbs`
- Create/use a particular Database: `use <db-name>`
- Show existing Collections: `show collections`
- Create/use a particular Collection: `db.<collection>`
- Add documents: `db.<collection>.insertOne({name: "Ram", age: 18})`
- Find documents in a collection: `db.<collection>.find(<attribute>)`
- Find specific document: `db.<collection>.findOne({name: "Ram"})`
- Update document: `db.<collection>.updateOne({name: 'Ram'}, {$set: {hobbies: ["Anime", "cooking"]}})`

### Embedded Documents
Let's say we had a database of students, we can switch to that db with the command:
```
use new_db
```
 If new_db does not exist, now it does.

add a collection name students by running the command:
```
db.students
```

if we wish to update and add another object as an attribute in the document (which is already a JSON object), run the following command:
```
db.students.updateOne({name: 'Ram'}, {$set: {idCards:{ hasAadharCard:true}}})
```

To add hobbies to all, use:
```
db.students.updateMany({}, {$set: {hobbies: ["Anime", "Manga"]}})
```

> [!tip] TIP: No need to specify attribute type!
> When querying to find students by hobby, there is no reason/need to specify the attribute's data type. MongoDB is intelligent enough to not give a fuck.

Now, when we wish to run a query to FIND a document on the basis of the value of a nested document inside it, we use `'key.nestedKey': value` logic as showcased in the given example:
```
db.students.find({'idCards.hasAadharCard': true})
```

Similarly, we can nest a conditional inside as an embedded document when finding records.
For example, the line below aims to find students who are younger than 12 (i.e., 11 or less)
```
db.students.find({age: {$lt: 12}})
```

### CRUD Operations
***==Create:==*** `insertOne(data, options)`, `insertMany(data, options)` and the new function `bulkWrite(data, options)`. 

> [!tip] Function `insertMany()` uses arrays
> Documents need to be inserted as an array or list in JSON when using `insertMany()`

***==Read:==*** `find(filter, options)` and `findOne(filter, options)` for ***Reading*** a document.

***==Update:==*** `updateOne(filter, data, options)`,  `updateMany(filter, data, options)` and the `replaceOne(filter, data, options)` 

***==Delete:==*** `deleteOne(filter, options)` and `deleteMany(filter, options)`

The difference between them is the distinction of how many matching elements need to be operated on. If only 1 document matches the criteria for deletion in `deleteMany` only that will be deleted, multiple documents match, all of them are gone but if many documents match the delete criteria and the function is `deleteOne`, it will only delete 1 depending upon which one ranks highest and let others go.

Similarly the function named `find()` returns an array with a cursor/pointer with which I can iterate on said array. Functions like `findOne()` can for the same reason not use `.count()` in front of them as well.

---
# Footnotes