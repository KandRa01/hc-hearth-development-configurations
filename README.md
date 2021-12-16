# Setting up & Running Apps 

- [MBS Mock Authorization](https://github.com/israelaltamira/hc-hearth-development-configurations/blob/main/auth-mock.md) 
- [SOAP ESP Mock Keepcontact and Socio Indicators](https://github.com/israelaltamira/hc-hearth-development-configurations/blob/main/esp-mock.md)
- Keep Contact Enrichment
- Socio Indicators Enrichment
- Metadata Payer
- Metadata InstructionSet
- JPA Server
- Process Engine (FHIR SERVER)

## Summary for all apps


|App|Port|Command
--- | --- | --
|Mock MBS Auth|8088| ./start-cloudconfig.sh local mock-token-authz.yml 'C:/\<path\>/hc-common-mock-token-authz-server-config' mocktokens |
|Mock ESP KC/Socio|8712| ./start-cloudconfig.sh local mock-esp-ws.yml 'C:/\<path\>/hc-common-mock-esp-ws-config-official' [mockkeepcontactresults\|mocksocioindicators] |
|Payer Metadata|8080/8081| ./start-cloudconfig.sh local hearth-api-metadata-payer-profile.yml 'C:/\<path\>/hc-hearth-api-metadata-payer-profile-config-official' dev |
|InstructionSet Metadata|8082/8083| mvn spring-boot:run |
|Enrichment Keep Contact|8090/8091| ./start-cloudconfig.sh local hearth-api-keepcontact.yml 'C:/\<path\>/hc-hearth-api-keepcontact-config' dev|
|Enrichment Socio|8092/8093| ./start-cloudconfig.sh local hearth-api-socio.yml 'C:/\<path\>/hc-hearth-api-socio-config-official' dev |
|JPA-server|9090| **1)** docker build -t hapi-jpa:1.0 . **2)** docker run -i --rm -p 9090:8080 --name plain-server hapi-jpa:1.0 |
|PE|9092/9093| mvn spring-boot:run |
 
## How to build dependencies
  1. enter to repository you are looking dependencies.
  2. switch to the tags tab and then inspect pom.xml file to see if this is the correct version you are looking for.
  3. then run next command to create a new branch from the tag and compile the project.
  
     git checkout tags/**\<tag\>** -b **\<branch\>**
  
## Diagrams
![image](https://user-images.githubusercontent.com/91071726/145665069-f0059369-d120-4afe-9f36-9e033b8bd890.png)
