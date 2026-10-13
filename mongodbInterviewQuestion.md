# MongoDB Interview Question & Answer  

## Q 1: What is MongoDB?  

***Answer:***  
`MongoDB` is a `NoSQL` database that stores data in flexible, document-based format instead of traditional rows and columns.  
It stores data as documents in `BSON` format, which is similar to `JSON`. These documents are organized into collections.  
*For example,* in an employee management system, we can store employee details like name, email, salary, and department in a MongoDB document.  
`MongoDB` is useful because it supports flexible data structures and makes it easy to store and manage application data.  
In simple words, `MongoDB` is a database that stores data in documents instead of tables and rows, and we use it to store, retrieve, update, and delete application data.  

---
---

## Q 2: Why is MongoDB called a NoSQL database?  

***Answer:***  
`MongoDB` is called a `NoSQL` database because it does not store data in traditional relational tables with fixed rows and columns like `SQL` databases. 
Instead, it stores data in documents using BSON format, and these documents are organized into collections. Its document structure is flexible, so documents in the same collection can have different fields when needed.  
`For example,` one employee document can contain a department field, while another document may not have that field.  
In simple words, `MongoDB` is called a `NoSQL` database because it stores data in flexible documents instead of traditional relational tables.  


----
----

## Q 3: MongoDB vs SQL database — what is the difference?

***Answer***  
`MongoDB` and `SQL` databases are both used to store and manage application data, but they store data differently.  
`SQL` databases, such as `MySQL`, store data in tables with rows and columns and usually use a predefined schema.  
`MongoDB` is a `NoSQL` database that stores data in BSON documents organized into collections. Its document structure is more flexible, so documents in the same collection can have different fields.  
Another difference is that `SQL` databases commonly use joins to work with related tables, while `MongoDB` supports embedded documents and references to manage related data. 
*For example,* in an employee management system, `MySQL` stores employee details in tables, while MongoDB can store them as documents.  
In simple words, `SQL` databases use tables and a structured schema, while `MongoDB` uses flexible documents. The best choice depends on the application's data and requirements.  

----
----

## Q 4: Why would you choose MongoDB?  

***Answer:***  
I would choose MongoDB when an application needs a flexible data structure and works with document-based data.  
MongoDB stores data in BSON documents, so we can easily manage data with different fields without requiring every document to have exactly the same structure.  
It also supports indexing for faster queries, aggregation for data processing, and horizontal scaling when an application needs to handle more data and traffic.  
*For example,* in an employee management system, we can use MongoDB to store employee details, addresses, and other related information in a flexible document structure.  
In simple words, I would choose MongoDB when the application's data structure needs flexibility, and its document-based approach fits the project requirements.  

----
----

## Q 5: What is a collection?  

***Answer:***  
A collection in MongoDB is a group of related documents, similar to a table in a SQL database.  
It stores documents that usually belong to the same category. Unlike SQL tables, documents in a MongoDB collection can have different fields and structures.  
*For example,* in an employee management system, we can create an employees collection to store employee details such as name, email, salary, and department.  
In simple words, a collection is a place in MongoDB where we store and organize related documents.  

-----
-----

## Q6: What is a document?  

***Answer:***  
A document in MongoDB is a single record that stores data in the form of field-value pairs, similar to a JSON object. MongoDB stores documents in BSON format.  
Each document can contain different types of data, such as strings, numbers, arrays, objects, and dates.  
*For example,* in an employee management system, one employee's details, such as name, email, and salary, can be stored in a single document.  
*For Example*   
```
{
  name: "Anshul",
  email: "anshul@example.com",
  salary: 30000
}
```  
In simple words, a document is a single record in MongoDB that contains related information about an item, such as an employee or a user.  

----
----

## Q 7: What is BSON?  

***Answer:***  
BSON stands for Binary JSON. It is a binary format used by MongoDB to store and represent documents.  
BSON is similar to JSON, but it supports additional data types, such as ObjectId and Date, and stores data in a format that MongoDB can process efficiently.  
*For example,* when we store an employee's details in MongoDB, we may write the data in a JSON-like format, but MongoDB stores the document internally in BSON format.  
In simple words, BSON is a binary format used by MongoDB to store documents, with support for more data types than JSON.  

----
----

## Q 8: What is _id in MongoDB? 

***Answer:***  
_id is a special field in MongoDB that uniquely identifies each document within a collection.  
When we insert a document without providing an _id, MongoDB automatically generates a unique ObjectId for it. We can also provide our own _id, but its value must be unique within that collection.  
*For example,* in an employee collection, each employee document has an _id that we can use to find, update, or delete that specific employee.  
In simple words, _id is the unique identifier of a document in MongoDB, similar to a primary key in a SQL database.  

----
----

## Q 9: What is ObjectId?  

***Answer:***  
ObjectId is a special data type in MongoDB that is commonly used to generate unique identifiers for documents.  
It is 12 bytes long and contains information such as a timestamp, a random value, and a counter. MongoDB automatically generates an ObjectId for the _id field when we insert a document without providing an ID.  
*For example,* when we create a new employee, MongoDB can generate an ObjectId that we use to find, update, or delete that employee.  
In simple words, ObjectId is a unique identifier commonly used for the _id field in MongoDB to identify individual documents.  

----
----

## Q 10: What is CRUD in MongoDB?  

***Answer:***  
CRUD stands for Create, Read, Update, and Delete. These are the four basic operations used to manage data in MongoDB.  
- `Create:` To insert new documents using insertOne() or insertMany().  
- `Read:` To retrieve documents using find() or findOne().  
- `Update:` To modify existing documents using updateOne() or updateMany().  
- `Delete:` To remove documents using deleteOne() or deleteMany().  
For example, in an employee management system, we can add a new employee, view employee details, update their salary, and delete their record using these operations. 
In simple words, CRUD operations allow us to create, read, update, and delete data stored in MongoDB.  

----
----

## Q 11: How do you insert a document?  

***Answer:***  
In MongoDB, we use insertOne() to insert a single document and insertMany() to insert multiple documents into a collection.  
For example, if we want to add a new employee to the employees collection, we can use the insertOne() method.  
*For Example*  
```
db.employees.insertOne({
  name: "Anshul",
  email: "anshul@example.com",
  salary: 30000
});
```  
Here, MongoDB inserts the employee document into the employees collection and automatically generates an _id if we don't provide one.  
In simple words, insertOne() adds one document, while insertMany() adds multiple documents to a MongoDB collection.  


----
----

## Q 12: How do you find documents? 

***Answer:***  
In MongoDB, we use the find() method to retrieve multiple documents and the findOne() method to retrieve a single matching document from a collection.  
*For example,* if we want to find all employees in the employees collection, we can use:  
```
db.employees.find();
```  
If we want to find employees from the IT department, we can use:  
```
db.employees.find({ department: "IT" });
```   
Here, MongoDB returns documents that match the given condition.  
In simple words, find() retrieves all matching documents, while findOne() returns only the first matching document.  

-----
-----

## Q 13: Difference between find() and findOne()?  

***Answer":***  
In MongoDB, both find() and findOne() are used to retrieve documents from a collection, but they return different results.  
find() returns a cursor that allows us to access all documents matching the given condition.  
findOne() returns only the first matching document, or null if no document matches.  
*For example,* if we want to fetch all employees from the IT department, we use find(). If we want to fetch only one employee from the IT department, we use findOne().  
```
db.employees.find({ department: "IT" });

db.employees.findOne({ department: "IT" });  
```  
In simple words, find() retrieves all matching documents, while findOne() retrieves only the first matching document.  

----
----

## Q 14: How do you update a document?  

***Answer:***  
In MongoDB, we use updateOne() to update a single document and updateMany() to update multiple documents that match a condition.  
We commonly use the $set operator to update specific fields without replacing the entire document.  
*For example,* if we want to update an employee's salary, we can write:  
```
db.employees.updateOne(
  { name: "Anshul" },
  { $set: { salary: 40000 } }
);
```  
Here, MongoDB finds an employee named Anshul and updates the salary to 40000, while keeping the other fields unchanged.  
In simple words, updateOne() updates one matching document, while updateMany() updates all matching documents.  

----
----

## Q 15: Difference between updateOne() and updateMany()?  

***Answer:***  
In MongoDB, both updateOne() and updateMany() are used to update documents, but they differ in how many documents they update.  
updateOne() updates only the first document that matches the given condition.  
updateMany() updates all documents that match the given condition.  
*For example,* if we want to update the salary of one specific employee, we can use updateOne(). If we want to update the department of all employees who belong to a particular department, we can use updateMany().  
```
db.employees.updateOne(
  { name: "Anshul" },
  { $set: { salary: 40000 } }
);

db.employees.updateMany(
  { department: "IT" },
  { $set: { department: "Engineering" } }
);
```  
In simple words, updateOne() updates one matching document, while updateMany() updates every matching document.  

----
----

## Q 16: How do you delete a document?  


***Answer***  
In MongoDB, we use deleteOne() to delete a single document and deleteMany() to delete all documents that match a given condition.  
*For example,* if we want to delete an employee by their name, we can use:  
```
db.employees.deleteOne({
  name: "Anshul"
});
```  
Here, MongoDB deletes the first document that matches the given condition.  
If we want to delete multiple matching documents, we use deleteMany().  
In simple words, deleteOne() deletes one matching document, while deleteMany() deletes all matching documents from a collection.  

----
----

## Q 17: What are MongoDB query operators? 

***Answer:***  
MongoDB query operators are special keywords that help us filter and find documents based on specific conditions.  
We use them to compare values, combine conditions, and check whether fields exist in a document.  
- $gt — greater than  
- $gte — greater than or equal to  
- $lt — less than  
- $lte — less than or equal to  
- $in — matches any value from a given list  
- $ne — not equal to  
- $or — matches at least one condition  
*For example,* to find employees whose salary is greater than ₹30,000, we can write:  
```
db.employees.find({
  salary: { $gt: 30000 }
});  
```  
In simple words, query operators help us retrieve specific documents from MongoDB by applying conditions to the data.

----
----

## Q 18: What is $gt, $gte, $lt, $lte, $in?  

***Answer:***  
These are MongoDB query operators used to filter documents based on specific conditions.  
- `$gt` means greater than.  
- `$gte` means greater than or equal to.  
- `$lt` means less than.  
- `$lte` means less than or equal to.  
- `$in` checks whether a field's value matches any value in a given list.  
*For example,* to find employees whose salary is greater than ₹30,000, we use:  
```
db.employees.find({
  salary: { $gt: 30000 }
});
```  
To find employees whose department is either IT or HR, we use:  
```
db.employees.find({
  department: { $in: ["IT", "HR"] }
});
```  
In simple words, these operators help us filter MongoDB documents using comparison conditions and a list of possible values.  


----
----

## Q 19: What is indexing in MongoDB?

***Answer:***  
Indexing in MongoDB is a technique used to make data retrieval faster. An index stores information about specific fields so MongoDB can find matching documents without scanning every document in a collection.  
*For example,* if we frequently search for employees by email, we can create an index on the email field to make those searches faster.  
```
db.employees.createIndex({ email: 1 });
```  
Here, 1 means ascending order. Indexes improve read performance, but they also require storage and can slow down insert, update, and delete operations because the indexes may need to be updated.  
In simple words, indexing helps MongoDB find data faster, especially in large collections.  


-----
-----

## Q 20: Why do we use indexes?

***Answer:***  
We use indexes in MongoDB to make data retrieval faster. Without an index, MongoDB may need to scan every document in a collection to find matching data.  
*For example,* in an employee management system, if we frequently search for employees by email, creating an index on the email field helps MongoDB find the matching employee more efficiently.  
However, indexes also use extra storage and can slow down insert, update, and delete operations because MongoDB needs to maintain them.  
In simple words, we use indexes to improve query performance, especially when searching large amounts of data.  


----
----

## Q 21: What is a compound index?

***Answer:***  
A compound index in MongoDB is an index created on two or more fields in a document.  
We use it when we frequently search or filter data using multiple fields together. It helps MongoDB find matching documents more efficiently for supported queries.  
*For example,* in an employee management system, if we frequently search employees by department and salary, we can create a compound index: 
```
db.employees.createIndex({
  department: 1,
  salary: 1
});
```  
Here, MongoDB creates an index on both department and salary. The order of fields matters because it affects which queries can efficiently use the index.  
In simple words, a compound index helps improve query performance when we search using multiple fields together.  

----
----

## Q 22: What is MongoDB aggregation?

***Answer:***  
MongoDB aggregation is used to process and analyze data from a collection and return meaningful results.  
It uses an aggregation pipeline, where documents pass through different stages to perform operations like filtering, grouping, sorting, and calculating totals.  
*For example,* in an employee management system, we can use aggregation to calculate the average salary of employees in each department.  
```
db.employees.aggregate([
  {
    $group: {
      _id: "$department",
      averageSalary: { $avg: "$salary" }
    }
  }
]); 
```  
Here, `$group` groups employees by department, and `$avg` calculates the average salary for each department.  
In simple words, aggregation helps us process data and generate useful results, such as totals, averages, and grouped reports.  


----
----

## Q 23: What is an aggregation pipeline? 

***Answer:***  
An aggregation pipeline is a sequence of stages in MongoDB where documents pass through different stages, and each stage performs a specific operation on the data.  
We use it to filter, group, sort, and calculate data to get meaningful results.  
For example, in an employee management system, we can first filter employees from the IT department using $match and then group them by department using $group to calculate their average salary.  
Each stage processes the data and passes its result to the next stage.  
In simple words, an aggregation pipeline processes data step by step to generate useful results from a MongoDB collection.