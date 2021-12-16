## MBS Mock Authorization

|  |  |
--- | --- 
|Code Repository |[hc-common-mock-token-authz-server]( https://github.com/LexisNexis-RBA/hc-common-mock-token-authz-server) |
|Config Repository |[hc-common-mock-token-authz-server-conf](https://github.com/LexisNexis-RBA/hc-common-mock-token-authz-server-conf) |
|Branch|v1||
|cmd|./start-cloudconfig.sh local mock-token-authz.yml 'C:/\<path\>/hc-common-mock-token-authz-server-config' mocktokens||

## Troubleshooting Mock Authorization
  ### Errors in request with bad characters:
  
  {"timestamp":"2021-11-19T13:58:52.821Z","status":400,"error":"Bad Request","message":"Not readable data","path":"/mock/token/authz/v1/authorizeuser"}
  
  This means extra invisible characters has been added to the request. Please look no extra whitespaces or EOL characters are present.
 
