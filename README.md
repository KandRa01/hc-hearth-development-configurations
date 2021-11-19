# Setting up & Running Apps 

- MBS Mock Authorization 
- SOAP ESP Mock Keepcontact
- Keep Contact Enrichment
- Socio Indicators Enrichment
- Metadata Payer
- Metadata InstructionSet
- JPA Server
- Process Engine (FHIR SERVER)

## Summary of ports


|App|Port|
--- | --- 
|Mock MBS Auth|8088|
|Mock ESP KC/Socio|8712|
|Payer Metadata|8080/8081|
|InstructionSet Metadata|8082/8083|
|Enrichment Keep Contact|8090/8091|
|Enrichment Socio|8092/8093|
|JPA-server|9090|
|PE|9092/9093|

## MBS Mock Authorization

|  |  |
--- | --- 
|Code Repository |[hc-common-mock-token-authz-server]( https://github.com/LexisNexis-RBA/hc-common-mock-token-authz-server) |
|Config Repository |[hc-common-mock-token-authz-server-conf](https://github.com/LexisNexis-RBA/hc-common-mock-token-authz-server-conf) |
|Branch|v1||
|cmd|./start-cloudconfig.sh local mock-token-authz.yml 'C:/<path>/hc-common-mock-token-authz-server-config' mocktokens||

## How to build dependencies
  1. enter to repository you are looking dependencies.
  2. switch to the tags tab and then inspect pom.xml file to see if this is the correct version you are looking for.
  3. then run next command to create a new branch from the tag and compile the project.
  
     git checkout tags/**\<tag\>** -b **\<branch\>**
  
## Troubleshooting Mock Authorization
  - Errors in request with bad characters:
  
  {"timestamp":"2021-11-19T13:58:52.821Z","status":400,"error":"Bad Request","message":"Not readable data","path":"/mock/token/authz/v1/authorizeuser"}
  
 
