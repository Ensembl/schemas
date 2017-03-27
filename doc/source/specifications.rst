Design Principles
!!!!!!!!!!!!!!!!!

High level design principles for revised GA4GH REST APIs.

These are starting points for discussion, as well as placeholders to remind us of future design decisions that need to be made.

Queries
@@@@@@@

* Where practical endpoints will use GET for queries
* Endpoints requiring more complex filters will be submitted using POST with a JSON encoded body

.. code-block::

  POST https://provider.org/api/findvariants/
  Content-Type: application/json

  {
    "biosample": {
      "biological_sex": "http://purl.obolibrary.org/obo/PATO_0020001",
      "population": ["1000GENOMES:phase_3:CEU", "1000GENOMES:phase_3:CHB"]
    },
    "disease": "EFO:0004330",
    "variation": "g.12:1234567G>T"
  }

* Providers may allow batch queries to an endpoint via POST and multiple JSON objects being combined in to an array
* If batch queries are allowed, the /endpoints endpoint must indicate this and the maximum number of items allowed per query
* Providers will reserve the /graphql endpoint for possible future GraphQL services

Data formats
@@@@@@@@@@@@

* Endpoints will return at minimum Protocol Buffers or JSON, both where possible
* JSON Schema will be used to define valid reponses for endpoints returning JSON
* Where applicable responses will use full ontology namespaces

Rate Limits
@@@@@@@@@@@

Exact definitions and calculation methods will be defined in a future specifications document.

* Providers may rate limit endpoints but must inform clients of these limits and the number of allowed queries remaining
* Providers may rate limit by number of requests over a given period using headers X-RateLimit-Limit, X-RateLimit-Reset, X-RateLimit-Period, and X-RateLimit-Remaining OR
* Providers may quantify the cost of different endpoints to clients and rate limit based on a number of "credits" for total requests per period using X-RateLimit-RequestCost, X-RateLimit-Remaining, X-RateLimit-Quota, X-RateLimit-Period, X-RateLimit-Reset headers
* Providers may limit simultaneous requests to an endpoint using the X-RateLimit-MaxConnections header

Data Discovery
@@@@@@@@@@@@@@

* Endpoints will accept a /schema suffix which will return the JSON Schema or Protocol Buffer definition based on the Accept header submitted
* Provider will have an /endpoints endpoint detailing in a yet to be determined machine readable format what subset of GA4GH endpoints are supported
* Detailed list of endpoints will indicate which are federated and what peer providers recursive queries will be performed against

Data Federation
@@@@@@@@@@@@@@@

Requirements for providers that will allow recursive queries.

* Provide a /peers endpoint to return a list of known peer providers in a machine readable format to be determined
* Providers may build a list of peers to use for recursive queries through an operator provided list OR
* Providers may build a list of peers to use for recursive queries through a seed list of peers and spidering across peers to discover all relevant peers
* If a provider performs a recursive lookup on peer providers, the returned results must list what peers were queried and the success or failure of each
* If a provider does not allow recusrive queries, it may return a list of known peers that provide the queries endpoint
* Providers must perform a periodic heartbeat to known peers and update their list of federated endpoints as appopriate

Security
@@@@@@@@

* Providers may require authentication for one or all endpoints, supported authentication schemes to be determined in follow up discussions
* Providers may list authentication requirements or usage restrictions per endpoint in the /endpoints endpoint
