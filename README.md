# Personal Knowledge Base

Storing data about people.


## Example of data

* contact manager type information : name, phone, address, ...
* photos related to people (taken_by, containing, ...)
* messages by people
* events attended by people : 
  * conferences
  * classes
  * meetings
* other kind of events :
  * clothe weared
  * meals
  * code written
* other kind of interesting information :
  * words known in languages
  * tv series watched
  * contacts
  * projects

## Technologies

* RDF graphes
* SPARQL
* triplestore independent but virtuoso will be used to start with

## Functionnalities expected

CRUD

* create data : SPARQL INSERT query
* read data : SELECT
* update data : UPDATE
* delete data : DELETE

It would be interesting to be able to download all the data in one click if needed.

## Architecture of the project

* backend : expose the SPARQL interface and a REST API to do the most simple things
* frontend : several ones are possibles for the various platform (pc, android) but start with a website
* importers : try and create importers from various data source into the graph
* exporters : export data back to the data sources

## Website

* A page for the documentation of the backend (which exposes the raw functionnalities)
* Some examples of information display from the knowledge base :
  * A list of people in the knowledge base
  * A page for the basic information about each person
  * A page for the tv series watched by that person
  * Using HybridQa to answer question in that KB

It would be nice to have some kind of general pages to display the triples of an entities like the DBpedia VAD.

The website doesn't have to know how to display everything from the knowledge base.

## Ontologies used

Use standard ontologies as often as possible. Examples :

* DBpedia ontology
* Yago ontology
* foaf ontology

If a property or a type doesn't exist in a standard ontology, create a new property/type and it would be nice to somehow store it in an owl file.

## Importers

Import data from : 

* FaceBook
* Google Contact
* trackt.tv
* memrise
* Hangout
* Messenger

These importers would be used in two ways :

* bulk import : import everything at a given time
* online importing : sync new data

Kind of possible ouputs :

* write turtle files
* execute SPARQL insert/update/delete queries

## Exporters

In order to make the knowledge base in sync with the rest of the services the user is using, it might be interesting to push back new information from the knowledge base to the services.

That part might be more complicated and it is not a priority.


## Permissions

Use graphs and virtuoso users to limit access to the right parts of the graph.

## Languages for implementation

Probably java for the backend and java or node.js for the frontend.

## Related works

* [Solid](https://github.com/linkeddata/SoLiD) : protocols to build social linked applications, interesting but it seems too broad to apply it here
* [Linked Data Platform](http://www.w3.org/TR/ldp/) : allow CRUD access to linked data
* [rww.io](https://github.com/deiu/rww.io) : RWW.IO is a personal Linked Data store
* [Facebook Open Graph](https://developers.facebook.com/docs/sharing/opengraph) : pretty solid technology, but sadly it's doesn't propose data in any standard way nor does it allow to put any kind of personalized information in it. And the third problem is it is a totally centralized software that cannot be stored elsewhere than on Facebook servers
* [Freebase / new Google knowledge graph API](https://developers.google.com/freebase/) : allow any personalized informations, but all the other problems of the Facebook Open Graph are there. However, it will be very interesting to see the possibilities of interaction between those and PersonalKnowledgeBase through importers, exporters and federated queries.
* Any interesting articles about that in the semantic web community ?


