# Configuring healthcare_immunization_registry_api Connector

## Initializing the connector

To use the healthcare_immunization_registry_api connector, add the <healthcare_immunization_registry_api.init> element in your configuration before carrying out any connector operations.
This <healthcare_immunization_registry_api.init> element authenticates the user using OAuth 2.0 Client Credentials Grant Type authentication to access the registered client application.
For more information on authorizing requests in healthcare_immunization_registry_api, see [API documentation](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).

**init**

```xml
<healthcare_immunization_registry_api.init>
    <base>{$ctx:base}</base>
    <clientId>{$ctx:clientId}</clientId>
    <clientSecret>{$ctx:clientSecret}</clientSecret>
    <tokenEndpoint>{$ctx:tokenEndpoint}</tokenEndpoint>
</healthcare_immunization_registry_api.init>
```

**Properties**

* base: The service root URL.
* accessToken: Represents the authorization of a specific application to access specific parts of a user’s data.
* clientId: Client ID of the registered application.
* clientSecret: Client secret of the registered application.
* tokenEndpoint: An HTTP endpoint that can be uses to obtain an access token.
* scope: The scope of the resources that will be accessed.

**Additional Info**
* For information on setting parameters to Property Mediators, see
[Property Mediator](https://ei.docs.wso2.com/en/7.2.0/micro-integrator/references/mediators/property-Mediator/).
