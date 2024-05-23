# MongoDB

Exploring simple commands using examples:

Un-normalised- use embedding

#### Creating a database
`use sparta`

#### Creating a collection called academy:
`db.createCollection("academy")`

#### Inserting one document
`db.academy.insertOne({“name”: “Kehinde”})`

#### Inserting many documents
`db.academy.insertMany([{ “firstname”: “Kehinde”, “lastname”:”Giwa”, “Stream”: “Data 402”}])`

#### Inserting many documents with an embedded document
`db.academy.insertMany([{“course”:”Data Engineering”, “length”:10}, {“course”:”Data Analysis”, “Length”:8}])`

#### Inserting one document with an embedded document
`db.academy.insertOne({name: "Luke", course: "Data", trainer: {name: "Paula", expertise: "Data"}})`


Normalised— use referencing
Reference object id of the document
For many- to-many relationships

#### Clearing the screen
`Cls` 

#### Creating a new collection in sparta database called students:
`db.createCollection("students")`

#### Setting validation rules
```
{
      $jsonSchema: {
         bsonType: "object",
         required: [ "name", "course" ],
      }
   }
```

#### Getting collection information
`db.getCollectionInfos`

#### Retrieving documents
`show collections`
or
`db.getCollectionNames()`

#### Returning all documents from a collection
`db.students.find({})`

#### Updating a document
`db.students.updateOne({name: “Mr s. Global”}, {$set:{score: 92.5, newfield: true}})`

#### Removing a field
`db.students.updateOne({name: “Mr S. Global”}, {$unset: {newField: null}})`

#### Updating many
`db.students.updateMany({}, {$set: {year: NumberInt(2025)} })`

#### Deleting a document
`db.students.deleteOne({name: “Mr S. Global”})`



### Exercise 1:
create database
`use sparta`

create collection
`db.createCollection("favouriteFilms")`

setting validation rules
With validation action as 'Error' and validation level as 'strict'

```
{
    $jsonSchema: {
    bsonType: 'object',
    required: [
        'title',
        'year',
        'genre'
        ]
    }
}
```

Inserting one
`db.favouriteFilms.insertOne({title: "Jurassic World", year: "2022", genre: "Sci-Fi"})`

Inserting many
`db.academy.insertMany([{ “title”: “Dune Part 2”, “year”: ”2024”, “genre”: “Sci-Fi”}, {"title": "Spider-Man: Across the Spider-Verse", "year": "2023", "genre": "Action" }])`