# Scripts for Fraunhofer Catalog

Scripts to acces the Fraunhofer catalog.

##  Get catalogs

```
curl --request GET \
  --url 'https://possible.fokus.fraunhofer.de/api/hub/repo/catalogues?valueType=identifiers' \
  --header 'User-Agent: insomnia/9.3.2'
```

##  Get datasets in catalog

```
curl --request GET \
  --url 'https://possible.fokus.fraunhofer.de/api/hub/repo/catalogues/<CATALOG_NAME>/datasets?=&valueType=identifiers'
```

For `CATALOG_NAME` use one of the catalogs from call "Get catalogs".

##  Inspect dataset

```
curl --request GET \
  --url https://possible.fokus.fraunhofer.de/api/hub/repo/datasets/<DATASET_ID>
```

For `DATASET_ID` use the ID from call "Get datasets in catalog".

##  Create dataset

```
curl --request POST \
  --url 'https://possible.fokus.fraunhofer.de/api/hub/repo/catalogues/<CATALOG_NAME>/datasets?valueType=identifiers' \
  --header 'Authorization: Bearer <TOKEN>' \
  --header 'Content-Type: application/ld+json' \
  --data '{
    "@graph": [
        {
            "@type": [
                "http://w3id.org/gaia-x/gax-trust-framework#DataResource",
                "dcat:Dataset"
            ],
            "dct:description": {
                "@language": "en",
                "@value": "<DESCRIPTION>"
            },
            "dct:title": {
                "@language": "en",
                "@value": "<TITLE>"
            }
        }
    ],
    "@context": {
        "dct": "http://purl.org/dc/terms/",
        "dcat": "http://www.w3.org/ns/dcat#"
    }
}'
```

For `CATALOG_NAME` use one of the catalogs from call "Get catalogs".

For `TOKEN` use the access token. 

For `DESCRIPTION` use a description.

For `TITLE` use a title.

##  Delete dataset

```
curl --request DELETE \
  --url https://possible.fokus.fraunhofer.de/api/hub/repo/datasets/<DATASET_ID> \
  --header 'Authorization: Bearer <TOKEN>'
```

For `TOKEN` use the access token. 

For `DATASET_ID` use the ID for the dataset to delete.

