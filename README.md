# Panatrans Dataset

Dataset of the public bus tranportation system of Ciudad de Panamá (Panamá).

## About
Panatrans is a collaborative project to allow the users of the panamenian public transport to create a dataset with the information of the stops and routes available in the City of Panama (which is currently inexistent).

This project is based in the premise that open software and open data are the key of innovation.

Related Projects that may interest you:

1. __[panatrans-api](https://github.com/merlos/panatrans-api)__: API that makes usage of this dataset.
2. __[panatrans-web](https://github.com/merlos/panatrans-web)__: A javascript web client and editor that makes usage of this API.

# Conventions and docs

In our __[Wiki](https://github.com/merlos/panatrans-dataset/wiki)__ you can find more about the naming conventions and the __[status of the dataset](https://github.com/merlos/panatrans-dataset/wiki/Estado-Rutas-Metrobus)__. Please, note that we write this documentation __in Spanish__.

# THE Dataset

This dataset is an extreme simplification of the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) defined by Google. 

![Conceptual model of a route](http://www.merlos.org/panatrans-api/conceptual_route.png "Conceptual model of a route")

There are 4 types of resources to represent a route (models, data types, objects or whatever you):

* __Stop__: Represents a bus stop. Includes a name and the (latitude, longitude) tuple.

* __Route__: Represents a bus route, for example: the route from Albrook to Miraflores.

* __Trip__: A route generally has one or two trips. For example, the route Albrook - Miraflores has two trips: (1) the trip from Albrook to Miraflores, and (2) the trip from Miraflores to Albrook. Each trip has a set of stops that may be the same or not. There may be some routes that only have a single trip (ie: circular routes or those that start and end at the same location). 

* __Stop_Sequence__: Links a trip with a stop to create an ordered list of stops. In the example, the trip Albrook to Miraflores has 4 stops, and therefore it has 4 `stop_sequences`, each one will link one of the stops with that trip. The first stop is Albrook (sequence = 0), then Diablo (sequence = 1), Ciudad del Saber (sequence = 2) and the last one Miraflores (sequence = 3).

These are the formats:

## stops.csv
| column        | type            | Description                         
| :------------:|:---------------:| ------------------------------------
| id            | INT             | Unique identifier of the stop       
| name          | STRING          | Name of the stop                    
| lat           | FLOAT(latitude) | Latitude of the stop location       
| lon           | FLOAT(longitude)| Longitude of the stop location 
| created_at    | DATE            | Date when the stop was created
| updated_at    | DATE            | Date when the stop was last updated 


## routes.csv
| column        | type          | Description                         
|:-------------:|:-------------:| ------------------------------------
| id            | INT           | Unique identifier of the route       
| name          | STRING        | Name of the route 
| url           | STRING        | Web address with more information of the page (usually at mibus.com.pa)
| created_at    | DATE          | Date when the route was created
| updated_at    | DATE          | Date when the route was last updated 


## trips.csv
| column        | type            | Description                         
| :------------:|:---------------:| ------------------------------------
| id            | INT             | Unique identifier of the trip     
| headsign      | STRING          | Some text to identify the trip                    
| route_id      | INT			        | Route this trip belongs to
| created_at    | DATE            | Date when the trip was created
| updated_at    | DATE            | Date when the trip was last updated 


## stop_sequences.csv
| column        | type            | Description                         
| :------------:|:---------------:| ------------------------------------
| id            | INT             | Unique identifier of the stop       
| sequence      | INT             | sequence number of the stop on the trip.
| trip_id       | STRING          | Id of the trip this sequence links                  
| stop_id       | INT			        | Id of the stop this sequence links
| created_at    | DATE            | Date when the stop was created
| updated_at    | DATE            | Date when the stop was last updated 


# License

__panatrans-dataset__ is made available under the __[Open Database License](http://opendatacommons.org/licenses/odbl/1.0/)__. Any rights in individual contents of the database are licensed under the __[Database Contents License](http://opendatacommons.org/licenses/dbcl/1.0/)__.

When using panatrans-dataset, credits should be publicly available:  

  _Panatrans-dataset © [www.panatrans.org](http://www.panatrans.org) contributors, distributed under [Open Database License](http://opendatacommons.org/licenses/odbl/1.0/)_


