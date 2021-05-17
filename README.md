# MongoDB
Show current databases.
```sh
	db
```

Select a database to use
```sh
	use database_name
```

Create a Collection
```sh
	db.myNewCollection.insertOne( { x: 1 } )
```

Create a Collection
```sh
	db.myNewCollection.createIndex( { y: 1 } )
```

## CREATE

Insert Data
```sh
	db.collection.insertOne( { x: 1 } )
```

Insert Data
```sh
	db.users.insertOne( 
		{ 
			name: "Douglas",
			year: "1987",
			status: "Working" 
		} 
	)
```

Insert Data
```sh
	db.inventory.insertMany([
	   { item: "journal", qty: 25, status: "A", size: { h: 14, w: 21, uom: "cm" }, tags: [ "blank", "red" ] },
	   { item: "notebook", qty: 50, status: "A", size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank" ] },
	   { item: "paper", qty: 10, status: "D", size: { h: 8.5, w: 11, uom: "in" }, tags: [ "red", "blank", "plain" ] },
	   { item: "planner", qty: 0, status: "D", size: { h: 22.85, w: 30, uom: "cm" }, tags: [ "blank", "red" ] },
	   { item: "postcard", qty: 45, status: "A", size: { h: 10, w: 15.25, uom: "cm" }, tags: [ "blue" ] }
]);


## READ

Select All Data
```sh
	db.inventory.find({})
```

Select All Data and show the maximum 5 items
```sh
	db.inventory.find({}).limit(5)
```

Select All Data and format the results
```sh
	db.inventory.find({}).pretty()
```

Select Specific Items
```sh
	db.inventory.find( { status: "D" } );
```

Select Specific Items
```sh
	db.inventory.find( { qty: 0 } );
```

Select Specific Items
```sh
	db.inventory.find( { qty: 0, status: "D" } );
```

Select Specific Items
```sh
	db.inventory.find( { "size.uom": "in" } )
```

Select Specific Items
```sh
	db.inventory.find( { size: { h: 14, w: 21, uom: "cm" } } )
```

Select Specific Items
```sh
	db.inventory.find( { tags: "red" } )
```

Select Specific Items
```sh
	db.inventory.find( { tags: [ "red", "blank" ] } )
```

Specify Fields to Return (Projection)
```sh
	db.inventory.find( { }, { item: 1, status: 1 } );
```

Specify Fields to Return (Projection)
```sh
	db.inventory.find( {}, { _id: 0, item: 1, status: 1 } );
```

## UPDATE

Update Data
```sh
	db.collection.updateOne()
```

Update Data
```sh
	db.collection.updateMany()
```

Update Data
```sh
	db.collection.replaceOne() 
```


## DELETE

Delete Database
```sh
	db.collection.deleteOne()
```
Delete Database
```sh
	db.collection.deleteMany()
```

Delete Database
```sh
	db.dropDatabase()
```
