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
* Fetch ancestry and/or ethnicity for an individual X
* Find all biosamples for an individual with a specific phenotype or disease (eg annotation of polydactyly)
* Find all biosamples by tissue or cell line
* Find all individuals that have X and not Y (negative filtering of result sets)
* Find all individuals with X using method Y (eg AML diagnosis with CGH array data and RNA-Seq)

Lookup
@@@@@@

* For a given name, what else is this feature known as (synonym lookup)

Metadata
@@@@@@@@

* For a dataset, what use restrictions apply (DUO ontology <https://github.com/EBISPOT/DUO> )
* Filter above result sets based on creation/update time (exact or range)

Reads/Sequence
@@@@@@@@@@@@@@

* Fetch associated reads/sequence for results set from above filters (second query or parameter to first query?)

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
* Return a list of servers recursive lookups are performed against (will this be by endpoint, as different servers may provide different subsets of defined endpoints?)
