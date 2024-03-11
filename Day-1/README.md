# MongoDB Tutorial

- show the databases in server : `show dbs;`
- use a database: `use database_name;`
Example:

    ```bash
    test> use employees;
    switched to db employees
    ```

## CRUD operations
- C - Create
- R - Read
- U - Update
- D - Delete

### C - Create
- you can use `db.inventory.insertOne()` to insert a single document while `db.inventory.insertMany()` to insert multiple documents.

Note: inventory is the database name, it can vary in your case.
Example:
    
```bash
employees> db.inventory.insertOne(
...     {
...         item: "canvas",
...         qty: 100, tags: ["cotton"],
...         size: { h: 28, w: 35.5, uom: "cm" }
...     }
... );
{
  acknowledged: true,
  insertedId: ObjectId('65eb44b24517869348172b55')
}
employees>
```

### R - Read
Fetch database information: `db.inventory.find()`
Note: `inventory` is the name of example database, you can use your own database name.

Example:

```bash
employees> db.inventory.find()
[
  {
    _id: ObjectId('65eb44b24517869348172b55'),
    item: 'canvas',
    qty: 100,
    tags: [ 'cotton' ],
    size: { h: 28, w: 35.5, uom: 'cm' }
  }
]
employees> db.inventory.find({qty: 100})
[
  {
    _id: ObjectId('65eb44b24517869348172b55'),
    item: 'canvas',
    qty: 100,
    tags: [ 'cotton' ],
    size: { h: 28, w: 35.5, uom: 'cm' }
  }
]
employees> 
```