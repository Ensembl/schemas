Use Cases
!!!!!!!!!

Variants
@@@@@@@@

* Allow one or more filters to be specified using logical operators
* Fetch all variants for males between 40 and 50 years old
* Find all variants by RSID 

Phenotype
@@@@@@@@@

* Find all features associated with sensitivity of GIST
* Find all associations with sensitivity of GIST in gene KIT
* Find all associations with non-Hodgkin's lymphoma, with RNA sequencing evidence in gene CD20
* Find all associations with disease <http://purl.obolibrary.org/obo/DOID_4> in a given feature

Sample queries
@@@@@@@@@@@@@@

* Query for individuals in cohorts using logical operators
* Fetch all biosamples for an individual X
* Fetch all biosamples for male individuals X
* Find all biosamples for an individual with an annotation of polydactyly (phenotype)

Lookup
@@@@@@

* For a given name, what else is this feature known as (synonym lookup)

Federated queries
@@@@@@@@@@@@@@@@@

* Allow user to request recursive lookups, which queries all servers it knows about to aggregate results (similar to DNS recursive queries)
* In returned results for recursive lookups, list the servers queries and success/failure of each
* Returns a list of peer/other servers that a server knows about, to assist with data discovery
* Return what servers would be queries for a recursive query 

Data discovery
@@@@@@@@@@@@@@

* What subset of the schema does query server provide, endpoints, object types returned
* Does server queried provide recursive lookups
* What servers does the queried server perform recursive lookups against?
