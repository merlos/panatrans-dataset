# Panatrans Dataset

Dataset of the public bus transportation system of Ciudad de Panamá (Panamá).

## About
Panatrans is a collaborative project to allow the users of the Panamanian public transport to create a dataset with the information of the stops and routes available in the City of Panama (which was inexistent at the time the project started).

This project is based on the premise that open software and open data are keys on innovation.

Panatrans is divided in four components:

1. __[gtfs_api](https://github.com/merlos/panatrans-dataset)__: The data model. It is an implementation of the [GTFS Specification](https://developers.google.com/transit/gtfs/reference/) in ruby on rails as an engine.  
2. __[panatrans-api]__ This project. It is the server side that populates a JSON API based on the data model of gtfs_api.
2. __[panatrans-web](https://github.com/merlos/panatrans-web)__: A javascript web client that makes usage of panatrans-api
3. __[panatrans-dataset](https://github.com/merlos/panatrans-dataset)__: It is the GTFS feed of the Panamanian public transport.

# THE Dataset
This dataset compatible with the [General Transit Feed Specification (GTFS)](https://developers.google.com/transit/gtfs/) defined by Google.

The source of this dataset is a KML that was published by MiBus on 2016 on its web page. The KML was parsed with __[panatrans-kml_extractor](https://github.com/merlos/panatrans-kml_extractor)__ and this is the result or parsing and some hand work on the output.

## v1.0.0 version
There was a first version of the dataset, which was an extremely simplification of the GTFS specification, can be found on the [v1.0.0 tag](https://github.com/merlos/panatrans-dataset/tree/v1.0.0).

# License
__panatrans-dataset__ is made available under the __[Open Database License](http://opendatacommons.org/licenses/odbl/1.0/)__. Any rights in individual contents of the database are licensed under the __[Database Contents License](http://opendatacommons.org/licenses/dbcl/1.0/)__.

When using panatrans-dataset, credits should be publicly available:  

  _Panatrans-dataset © [www.panatrans.org](http://www.panatrans.org) contributors, distributed under [Open Database License](http://opendatacommons.org/licenses/odbl/1.0/)_
