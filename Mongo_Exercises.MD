# MongoDB

Un-normalised- use embedding

db.createCollection("academy")
{ ok: 1 }


test> use sparta

db.academy.insertOne({... “name”: “Luke”...})

db.academy.insertMany([{“course”:”Data Engineering”, “length”:10}, {“course”:”Data Analysis”, “Length”:8}])


(Connect compass> new connection with connection string)

db.academy.insertMany([{ “firstname”: “Kehinde”, “lastname”:”Giwa”, “Stream”: “Data 402”}])



Embedding……
In mongosh
db.academy.insertOne({name: "Luke", course: "Data", trainer: {name: "Paula", expertise: "Data"}})


Normalised— use referencing
REference  object id of the document

For many- to-many relationships
(Clear screen)
Cls 

Create new collection in sparta database called students:
db.createCollection("students")
{ ok: 1 }

(go to validation)
(add validation rules)
(click add rule)
(validation action: Error, validation level: Strict)
(adding a simple schema)

[14:29] Luke Fairbrass
{

      $jsonSchema: {

         bsonType: "object",

         required: [ "name", "course" ],

      }

   }


db.getCollectionInfos

db.students.insertOne({name: “Mr S.Global”, year: NumberInt(2024), score: 88.2, address: {city:”Birmingham”}, course; “Data”})

Cls


(retrieving docs)

show collections
or
db.getCollectionNames()

(Returning all docs from a collection)

db.students.find({})

(updating a doc)

db.students.updateOne({name: “Mr s. Global”}, {$set:{score: 92.5, newfield: true}})

(removing a field)

db.students.updateOne({name: “Mr S. Global”}, {$unset: {newField: null}})

(Updating many)

db.students.updateMany({}, {$set: {year: NumberInt(2025)} })

(deleting a doc)

db.students.deleteOne({name: “Mr S. Global”})

Install mongodb database tools



