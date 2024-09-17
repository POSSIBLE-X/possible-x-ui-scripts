# possible-x-ui-scripts

A repository for different scripts.

## fraunhofer-catalog

This folder contains scripts for accessing backend systems. So these scripts are UI scripts which can be used instead of a graphical UI.

## wiremock-mappings

Mocks for Wiremock. Wiremock is a tool to easily mock a REST server. You can easily specify static responses for endpoints.

This folder contains configurations for mocking some calls to the EDC and to the FH Catalog.

You can run Wiremock via jar (which can be downloaded from the Wiremock site (https://wiremock.org/docs/download-and-installation/).

Run for example like this:
```
java -jar wiremock-standalone-3.9.1.jar --verbose --port 9090
```



