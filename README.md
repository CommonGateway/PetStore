# Pet Store API
[![Automated Testing](https://github.com/CommonGateway/PetStore/actions/workflows/tests.yml/badge.svg)](https://github.com/CommonGateway/PetStore/actions/workflows/tests.yml)

A example implementation of a Common Gateway configuration for generating an API. This example has been specifically setup to use as a template, read more about that under [Using this repository as a template](#Using this repositry as a temple).

- [API Defintion (redocly)](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/CommonGateway/PetStore/main/OAS.yaml&nocors)
- [API Defintion (file)](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml)
- [Publiccode](https://github.com/CommonGateway/PetStore/blob/main/publiccode.yaml)
- [Stoplight.io]([https://conduction.stoplight.io/studio/pet-store:main?](https://conduction.stoplight.io/docs/pet-store/branches/main/ls7mp80wwy88k-swagger-petstore))

## Create or edit your OpenAPI Specification

What is OpenAPI Specification

//TODO Elaborate

This template uses a OpenAPI Specification (OAS) as API definition in which your API can be defined and read from.

That OAS definition can be created with multiple tools. We recommend using [stoplight.io](https://stoplight.io), but you also use [Postman](https://www.postman.com) or a simple editor if you know the standard like https://editor.swagger.io.

To create a OAS with [stoplight.io](https://stoplight.io) follow these steps:

1. Register or login on [stoplight.io](https://stoplight.io).

2. Create a workspace

3. Navigate to projects in the top navigation or go to yourworkspacename.stoplight.io/admin/projects.

4. Create a new project by pressing 'New Project' button in the top right of the page.

5. If you want to create a new API create a blank project with a proper name.

6. If you want to edit a already existing API and you have the openapi file for that API you can choose to 'Import OpenAPI file'

7. Now you can create new paths (endpoints) and models (objects) in the bottom left window. 

8. To link a path with a model you can select a path, add or select a response, add or select body from that response, and then if this path is for collections select array as type with subtype $ref or if this path is for a single object select $ref as type. You can then find your created model and link it  

9. When satisfied with your API //TODO Elaborate


## About Common Gateway configuration files
Read more..

## Creating your own documentation

This Commmon Gateway configuration repository is bassed on [petstore](https://redocly.github.io/redoc/) an example [Open API Specification]([https://redocly.com/docs/openapi/reference-docs-example/overview/](https://swagger.io/specification/)) from our friends at [redocly](https://redocly.com/docs/). In order to create and maintain Open API Secifications files we recommend using [stoplight.io](https://stoplight.io), you can find the stoplight project for Pet Store [here](https://conduction.stoplight.io/docs/pet-store/branches/main/ls7mp80wwy88k-swagger-petstore). For convience purpose a copy of the Pet strore oas is stored in this repository [here](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml).

The [public code](https://yml.publiccode.tools/) for this ropository was genereted trough the [publiccode yaml editor](https://publiccode-editor.developers.italia.it/).

## Running the API locally

You need [Docker desktop](https://www.docker.com/) if you want to use this API locally on the [gateway](https://github.com/ConductionNL/commonground-gateway).
Once you have installed docker you need to go to the root of the project with a command line.

Then you can run the image with:

`docker compose up`

If the php container shows "Ready to handle connections" the gateway is ready.
The API runs on port :80 and the endpoints of this API fall under /api

## Running the API online

To run the API on a online gateway the helm secret PUBLICCODE must be set with the url to the raw publiccode.yaml, like: https://raw.githubusercontent.com/CommonGateway/PetStoreAPI/main/publiccode.yaml

If its properly set you can run the following command in a PHP pod:

`bin/console app:load-publiccodes`

The console should show if the API has been loaded successfully, and then you can make API requests to yourdomain/api.


## (Unit) Testing the API

On every commit github launches a action that generates a postman collection and tests the API. Its results can be viewed under Actions on the github page.

Make sure that in your OAS definition there is a localhost server defined like:
    
    servers:
     - url: localhost/api

## Using this repositry as a template
In order to use this repositry as a template hit ["Use this template"](https://github.com/CommonGateway/PetStore/generate) in the top right corner of the repository and select the user/organisation and name under wich you would like to setup your new repository. Afther you have created you new ropistory please follow the follwoing steps

1. Replace the OAS file in the repository root with your own api definition

2. Replace .github/workflows/tests.yml with:

        # This is an workflow to autmaticly tests the validity of your OAS definitons and the Common Gateway's abillity to provide an API for them
        name: Automated Testing

        # Controls when the workflow will run
        on:
          # Triggers the workflow on push or pull request events but only for the "main" branch
          push:
            branches: [ "main" ]
          pull_request:
            branches: [ "main" ] 

          # Allows you to run this workflow manually from the Actions tab
          workflow_dispatch:

        # Uses the default testing workflow from https://github.com/CommonGateway/PetStoreAPI
        jobs:
          call-testing-workflow-from-default-pet-store-api:
            uses: CommonGateway/PetStoreAPI/.github/workflows/tests.yml@main

3. Open the public code file and update the name, description and urls accordingly (dont foget to update the urls in the description section)

4. Open the readme.md file alter it to suit your project (don't forget to update the url of the status badge)

5. If you want your API to be downloadable trough the Common Gateway API store make sure that your repository is set to public
