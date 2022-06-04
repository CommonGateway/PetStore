# Pet Store 
[![Automated Testing](https://github.com/CommonGateway/PetStore/actions/workflows/tests.yml/badge.svg)](https://github.com/CommonGateway/PetStore/actions/workflows/tests.yml)

A example implementation of a Common Gateway configuration for generating an API. This example has been specifically setup to use as a temple, read more about that under [Using this repositry as a temple](#Using this repositry as a temple).

- [API Defintion (redocly)](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/CommonGateway/PetStore/main/OAS.yaml&nocors)
- [API Defintion (file)](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml)
- [Publiccode](https://github.com/CommonGateway/PetStore/blob/main/publiccode.yaml)

## About Common Gateway configuration files
Read more..

## Creating your own documentation
This Commmon Gateway configuration repository is bassed on [petstore](https://redocly.github.io/redoc/) an example [Open API Specification]([https://redocly.com/docs/openapi/reference-docs-example/overview/](https://swagger.io/specification/)) from our friends at [redocly](https://redocly.com/docs/). In order to create and maintain Open Api Secifications files we recomend using [stoplight](), you can find the stoplight project for Pet Store [here](https://conduction.stoplight.io/docs/pet-store/branches/main/ls7mp80wwy88k-swagger-petstore). For convience purpose a copy of the Pet strore oas is stored in this repository [here](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml).

The [public code](https://yml.publiccode.tools/) for this ropository was genereted trough the [publiccode yaml editor](https://publiccode-editor.developers.italia.it/).

## Running the API localy

## Running the API online

## (Unit) Testing the API

## Using this repositry as a temple
In order to use this repositry as a template hit ["Use this template"](https://github.com/CommonGateway/PetStore/generate) in the top right corner of the repository and select the user/organisation and name under wich you would like to setup your new repository. Afther you have created you new ropistory please follow the follwoing steps

1. Replace the OAS file in the repository root with your own api definition
2. Open the public code file and update the name, description and urls accordingly (dont foget to update the urls in the description section)
3. Open the readme.md file alter it to suit your project (don't forget to update the url of the status badge)
4. If you want your API to be downloadable trough the Common Gateway API store make sure that your repository is set to public