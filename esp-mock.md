## ESP Mock app

|  |  |
--- | --- 
|Code Repository |[hc-common-mock-esp-ws]( https://github.com/LexisNexis-RBA/hc-common-mock-esp-ws) |
|Config Repository |[hc-common-mock-esp-ws-conf](https://github.com/LexisNexis-RBA/hc-common-mock-esp-ws-conf) |
|clone app repo | git clone git@github.com:LexisNexis-RBA/hc-common-mock-esp-ws.git||
|clone config repo | git clone git@github.com:LexisNexis-RBA/hc-common-mock-esp-ws-config.git||
|Branch| master ||
|cmd (KC)|./start-cloudconfig.sh local mock-esp-ws.yml 'C:/\<path to your repo\>/hc-common-mock-esp-ws-config' mockkeepcontactresults ||
|cmd (Socio)|./start-cloudconfig.sh local mock-esp-ws.yml 'C:/\<path to your repo\>/hc-common-mock-esp-ws-config' mocksocioindicators ||


## Running the app
1) please check if you have these repo's
- hc-common-mock-esp-ws
- hc-common-mock-esp-ws-config

2) then please compile with maven and try to run it with any of the next lines:

for keepcontact:
- ./start-cloudconfig.sh local mock-esp-ws.yml 'C:/?/hc-common-mock-esp-ws-config-official' mockkeepcontactresults

for socio:
- ./start-cloudconfig.sh local mock-esp-ws.yml 'C:/?/hc-common-mock-esp-ws-config-official' mocksocioindicators

3) please download and install SoapUi so you can do some requests directly to the app

### Keepcontact - request sample

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:lnrisk:ws:wshealthcare:(internal)@ver=3.01">
   <soapenv:Header/>
   <soapenv:Body>
      <urn:KeepContactReportRequest>
      	<urn:Options>
            <urn:IncludeAddressProcess>true</urn:IncludeAddressProcess>
            <urn:IncludeDeceasedProcess>true</urn:IncludeDeceasedProcess>
            <urn:IncludeEmailProcess>true</urn:IncludeEmailProcess>
            <urn:IncludePhoneProcess>true</urn:IncludePhoneProcess>
         </urn:Options>
         <urn:ReportBy>
            <urn:Name>
               <urn:First>John</urn:First>
               <urn:Last>Doe</urn:Last>
            </urn:Name>
            <urn:SSN>857482967</urn:SSN>
         </urn:ReportBy>
      </urn:KeepContactReportRequest>
   </soapenv:Body>
</soapenv:Envelope>

### Socio indicators - request sample 
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:lnrisk:ws:wshealthcare:(internal)@ver=3.01">
   <soapenv:Header/>
   <soapenv:Body>
      <urn:SocioeconomicIndicatorsRequest>
         <urn:Options>
            <urn:IncludeReadmissionScore>true</urn:IncludeReadmissionScore>
            <urn:IncludeHealthAttributesV3>true</urn:IncludeHealthAttributesV3>
            <urn:IncludeMedicationAdherenceScore>true</urn:IncludeMedicationAdherenceScore>
            <urn:IncludeMotivationScore>true</urn:IncludeMotivationScore>
            <urn:IncludeTotalCostRiskScore>true</urn:IncludeTotalCostRiskScore>
         </urn:Options>
         <urn:Member>
            <urn:Name>
               <urn:First>Jane</urn:First>
               <urn:Last>Doe</urn:Last>
            </urn:Name>
            <urn:Address>
               <urn:StreetAddress1>Mulholland Drv 3600</urn:StreetAddress1>
               <urn:State>CA</urn:State>
               <urn:City>Culver City</urn:City>
               <urn:Zip5>90066</urn:Zip5>
            </urn:Address>
            <urn:Gender>f</urn:Gender>
         </urn:Member>
      </urn:SocioeconomicIndicatorsRequest>
   </soapenv:Body>
</soapenv:Envelope>

## Troubleshooting Mock Authorization
  ### .
 
