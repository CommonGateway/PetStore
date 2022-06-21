# Pet Store API

Here you can find an example of a Common Gateway configuration for generating an API. This example has been specifically set up to use as a template. Read more about that under [Using this repository as a template](#Using this repository as a temple).

- [API Definition (redocly)](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/CommonGateway/PetStore/main/OAS.yaml&nocors)
- [API Definition (file)](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml)
- [Public Code](https://github.com/CommonGateway/PetStore/blob/main/publiccode.yaml)
- [Stoplight.io]([https://conduction.stoplight.io/studio/pet-store:main?](https://conduction.stoplight.io/docs/pet-store/branches/main/ls7mp80wwy88k-swagger-petstore))

## Create or edit your OpenAPI Specification

What is OpenAPI Specification

The OpenApi Specification(OAS) defines a standard, language-agnostic interface to RESTful APIs, allowing humans and computers to discover and understand the service's capabilities without access to source code, documentation, or network traffic inspection. When properly defined, a consumer can understand and interact with the remote service with minimal implementation logic.

Documentation generation tools can then use an OpenAPI definition to display the API, code generation tools to generate servers and clients in various programming languages, testing tools, and many other use cases.

This template uses the (OAS) as an API definition for the reasons above.

### Creating the OAS

Writing the API standard yourself is very error-prone. We recommend using [Stoplight](https://stoplight.io) for the automatic generation of an OAS, but there's also [Postman](https://www.postman.com). For checking, there are also editors, like <https://editor.swagger.io>.

The OAS can be defined in both JSON and YAML. It shouldn't make a difference in most cases, and although we often work from a YAML-first basis, there have been times were working with JSON was superior.

That OAS definition can be created with multiple tools. We recommend using [stoplight.io](https://stoplight.io), but you also use [Postman](https://www.postman.com) or a simple editor if you know the standard like <https://editor.swagger.io>.

To create an OAS with [Stoplight](https://stoplight.io/), follow these steps:

- Register or log in on Stoplight.
- Create a workspace
- Navigate to projects in the top navigation or go to yourworkspacename.stoplight.io/admin/projects.
- Create a new project with the `New Project` button in the top right corner.
- If you want to create a new API, create a blank project with a proper name.
- If you want to edit an already existing API and you have the OpenApi file for that API, you can choose to `Import OpenAPI file`
<<<<<<< HEAD
- You can create new paths (endpoints) and models (objects) in the bottom left window.
- To link a path with a model, you can select a path, add or select a response, add or select `body` from that response, and then if this path is for collections, select `array` as a type with a subtype `$ref` or if this path is for a single object select `$ref` as type. You can then find your created model and link it

### Editing your OAS

If you created a new project, you can remove the example paths and models by right-clicking on these in the bottom left window and selecting 'Delete'. You can also keep these examples if you want to.

Firstly, you should create a model (object) which we can link to a path later. Right-click on 'Models' in the bottom left window and select 'New model'. Here you can define an object.

You can create paths (endpoints) by right-clicking on 'Paths' in the bottom left window and selecting 'New Path'. You can add multiple methods to your path by selecting one and pressing the + operation button.

To link a path with a model, you can select a path, add or select a response, add or select `body` from that response, and then if this path is an array of objects select array as type with subtype $ref or if this path is for a single object select $ref as type. In the $ref search box you can find and select your created models.

If you are satisfied with your created API you can save it by selecting 'Publish' in the top left of the page. Next, we want to export this OpenAPI Specification by righting clicking your .yaml file in the top left section of the page and selecting 'Export'. Choose the format YAML and press 'Save to file'.

Add the saved .yaml to your new API repository. Rename the downloaded file to OAS.yaml and go to the git page of this repository. Open OAS.yaml on github and overwrite it with your created OAS.yaml or [clone this repo to your computer](#Cloning this repository to your computer) and overwrite it in your favourite IDE and git commit/push it. //TODO could be better written

Your created OAS is now in your new API repository, you can always view or edit it through Stoplight and export it again.

## About Common Gateway configuration files

Read more..

## Creating OAS documentation

This Common Gateway configuration repository is based on [Petstore](https://redocly.github.io/redoc/). Petstore is an example Open API Specification from our friends at [Redocly](https://redocly.com/docs/). We recommend using [Stoplight](https://stoplight.io) for maintaining OAS specifications. You can find the Stoplight project for the Pet Store [here](https://conduction.stoplight.io/docs/pet-store/branches/main/ls7mp80wwy88k-swagger-petstore). For convenience, a copy of the Pet store OAS is found [here](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml).

We generated the public code for this repository with the Public Code [YAML](https://publiccode-editor.developers.italia.it/) editor

## Running the API locally

// TODO more explaination
You need [Docker desktop](https://www.docker.com/) if you want to use this API locally on the Gateway. Once you have installed Docker Desktop, go to the project's root with a command line.
Then you can run the image with:

`$ docker-compose up`

The Gateway is ready when the terminal displays the `"Ready to handle connections"`. The API runs on `port:80` and the endpoints of this API fall under `/api`

## Running the API online

// TODO more explaination
To run the API on a online Gateway, the `helm` secret `PUBLICCODE` must be set with the url to the raw `publiccode.yaml`, like:
`https://raw.githubusercontent.com/CommonGateway/PetStoreAPI/main/publiccode.yaml`

If set you can run the following command in a PHP pod:

`bin/console app:load-publiccodes`

The console should show if the API has been loaded successfully, and then you can make API requests to `[yourdomain]/api`.

## (Unit) Testing the API

// TODO new text about unit testing in gateway (still needs to be build in gateway?)
GitHub launches an action on every commit that generates a Postman collection and tests the API. You view the action results under `Actions` on the GitHub page.

// TODO this text should be moved to Create or edit your OpenAPI Specification
Make sure that in your OAS definition, there is a `localhost` server defined like:

```yaml
servers:
 - url: localhost/api
```

## Using this repository as a template

To use this repository as a template, hit `Use this template` in the top right corner of the repository and select the `user/organisation` and name under which you would like to set up your new repository. After creating your new repository, please follow these steps:

- Replace the OAS file in the repository root with your own OpenAPI Specification (see [create or edit your OpenAPI Specification](#Create or edit your OpenAPI Specification) if you dont have a OAS).
- Open the `publiccode` file and update the `name`, `description` and `urls` accordingly (dont forget to update the urls in the description section)
- Open the README.md file alter it to suit your project (don't forget to update the UR: of the status badge)
If you want your API to be downloadable through the Common Gateway API store make sure that your repository is set to public
