# SNOMED CT Tools v1
Useful tools to get up and running with SNOMED CT quickly.

There are currently two ways available to load and query SNOMED CT in your local environment:

* SNOMED CT Query Service
* SNOMED CT Snapshot Browser API

Both can be used in tandem or separately depending on your use case.

There are other options (including our Snow Owl Terminology Server) for more powerful use of SNOMED CT and these will be detailed in subsequent releases of the Vendor Toolkit.

## SNOMED CT Query service

The query service is very lightweight tool to load a SNOMED CT Snapshot into memory quickly and efficiently. It will then allow you to use the SNOMED CT Expression Constraint Language (ECL) to query the terminology. This makes this service very useful to get up and running with SNOMED CT without too much effort. It also provides a good development environment to try out ECL queries.

However, the main limitation it has in order to be able to be stored in memory is that the response to any query only contains the FSN and none the preferred terms from different language reference sets. It also only currently works with *editions* and not extensions on their own.

## SNOMED CT Snapshot Browser APIS

This service will store all of a SNOMED CT Snapshot release of either an edition or an extension. The difference between this and the Query Service is that it involves more steps and applications to deploy, the conversion of RF2 release to JSON and then the import into a MongoDB, as well as the deployment of node.js.

However, once deployed, it will allow you to text search descriptions and return all available concepts with their associated synonyms in the relevant language. It's limitation is the lack of full ECL support.

## Deployment Options

In order to have the powerful and quick ECL implementation, we have seen some users deploy the Query Service to get the results of ECL queries and then use the Snapshot Browser API to retrieve the full details of concepts on demand.
