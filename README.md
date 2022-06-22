# Pet Store API

This repository is an example of a [Common Gateway](https://github.com/CommonGateway) configuration for generating an [API](https://www.howtogeek.com/343877/what-is-an-api/). This example has been specifically set up to use as a template to create and use a API or setup and use a existing API. 

To start with creating or setting up a API start with [using this repository as a template](#Using-this-repository-as-a-template). This step will start and guide you through the process.

Quick links about this API:

- [API Documentation (redocly is a API documentation generator)](https://redocly.github.io/redoc/?url=https://raw.githubusercontent.com/CommonGateway/PetStore/main/OAS.yaml&nocors)
- [API Definition (yaml or json file)](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml)
- [Public Code (file about this API and makes it searchable)](https://github.com/CommonGateway/PetStore/blob/main/publiccode.yaml)
- [Stoplight.io (OAS editing tool)](https://conduction.stoplight.io/docs/pet-store)

## Using this repository as a template

To use this repository as a template, you will need a GitHub account. Make sure you have a GitHub account and are logged in on [GitHub](https://github.com). When you are logged in you can see a `Use this template` button in the top right corner of the repository and select the `user/organisation` and name under which you would like to set up your new repository. After creating your new repository, please follow these steps:

- Replace the OAS file in the repository root with [your own OpenAPI Specification](#your-openapi-specification).
- Open the `publiccode` file and update the `name`, `description` and `urls` accordingly (dont forget to update the urls in the description section)
- Open the README.md file alter it to suit your project (don't forget to update the UR: of the status badge)
If you want your API to be downloadable through the Common Gateway API store make sure that your repository is set to public


## Your OpenAPI Specification

What is a OpenAPI Specification

The OpenApi Specification(OAS) defines a standard, language-agnostic interface to RESTful APIs, allowing humans and computers to discover and understand the service's capabilities without access to source code, documentation, or network traffic inspection. When properly defined, a consumer can understand and interact with the remote service with minimal implementation logic.

Documentation generation tools can then use an OpenAPI definition to display the API, code generation tools to generate servers and clients in various programming languages, testing tools, and many other use cases.

This template uses the (OAS) as an API definition for the reasons above.

If you don't have a API OAS yet you can continue with [creating your oas](#creating-your-oas), if you already have a OAS but you want to edit you can go to [editing your oas](#editing-your-oas). If you have a API OAS defintion which is already ready, you can go to continue to [adding your OAS to your repository](#adding-your-oas-to-your-repository).

### Creating your OAS

Writing the API standard yourself is very error-prone. We recommend using [Stoplight](https://stoplight.io) for the automatic generation of an OAS, but there's also [Postman](https://www.postman.com). For checking, there are also editors, like <https://editor.swagger.io>.

The OAS can be defined in both JSON and YAML. It shouldn't make a difference in most cases, and although we often work from a YAML-first basis, there have been times were working with JSON was superior.

To create your OAS with [Stoplight](https://stoplight.io/), follow these steps:

- Register or log in on Stoplight.
- Create a workspace or use a existing one.
- Navigate to projects in the top navigation or go to yourworkspacename.stoplight.io/admin/projects.
- Create a new project with the `New Project` button in the top right corner.
- To create a new API, create a blank project with a proper name.
- You can create new paths (endpoints) and models (objects) in the bottom left window.
- To link a path with a model, you can select a path, add or select a response, add or select `body` from that response, and then if this path is for collections, select `array` as a type with a subtype `$ref` or if this path is for a single object select `$ref` as type. You can then find your created model and link it.
- If you are satisfied with your created API you can save it by selecting 'Publish' in the top left of the page. Next, we want to export this OpenAPI Specification by righting clicking your .yaml file in the top left section of the page and selecting 'Export'. Choose the format YAML and press 'Save to file'.

You have now downloaded your OpenAPI Specification (OAS). Continue to [adding your OAS to your repository](#adding-your-oas-to-your-repository).

### Editing your OAS

To edit your OAS with [Stoplight](https://stoplight.io/), follow these steps:

- Register or log in on Stoplight.
- Create a workspace or use a existing one.
- Navigate to projects in the top navigation or go to yourworkspacename.stoplight.io/admin/projects.
- Create a new project with the `New Project` button in the top right corner.
- To edit an already existing API and you have the OpenAPI file for that API, you can choose to `Import OpenAPI file`.
- Firstly, you should create a model (object) which we can link to a path later. Right-click on 'Models' in the bottom left window and select 'New model'. Here you can define an object.
- You can create paths (endpoints) by right-clicking on 'Paths' in the bottom left window and selecting 'New Path'. You can add multiple methods to your path by selecting one and pressing the + operation button.
- To link a path with a model, you can select a path, add or select a response, add or select `body` from that response, and then if this path is an array of objects select `array` as type with subtype `$ref` or if this path is for a single object select `$ref` as type. In the `$ref` search box you can find and select your created models.
- If you are satisfied with your created API you can save it by selecting 'Publish' in the top left of the page. Next, we want to export this OpenAPI Specification by righting clicking your .yaml file in the top left section of the page and selecting 'Export'. Choose the format YAML or JSON and press 'Save to file'.

You have now downloaded your OpenAPI Specification (OAS). Continue to [adding your OAS to your repository](#adding-your-oas-to-your-repository).

### Adding your OAS to your repository

Rename the downloaded OAS file to OAS.yaml and go to the git page of this repository. Open OAS.yaml on github and overwrite it with your created OAS.yaml.

Your created OAS is now in your new API repository. You can always view or edit it through Stoplight and export it again, then overwriting the OAS.yaml in your repository.

// TODO how to add oas to repository

## About Common Gateway configuration files

Read more..

<!-- ## Creating OAS documentation

This Common Gateway configuration repository is based on [Petstore](https://redocly.github.io/redoc/). Petstore is an example Open API Specification from our friends at [Redocly](https://redocly.com/docs/). We recommend using [Stoplight](https://stoplight.io) for maintaining OAS specifications. You can find the Stoplight project for the Pet Store [here](https://conduction.stoplight.io/docs/pet-store/branches/main/ls7mp80wwy88k-swagger-petstore). For convenience, a copy of the Pet store OAS is found [here](https://github.com/CommonGateway/PetStore/blob/main/OAS.yaml).

We generated the public code for this repository with the Public Code [YAML](https://publiccode-editor.developers.italia.it/) editor -->

## Running the API locally

Running this API can be done through various ways. If you are familiar with Docker and Git, you can execute the commande needed. For those not familair, below is a detailed walkthrough.

```bash
git clone https://github.com/CommonGateway/PetStoreAPI.git
cd PetStoreAPI
docker-compose up
```

To run and test this API locally you first clone this repository to your local computer. You will need to have [Git](https://git-scm.com/download/win) installed or any [Git GUI](https://git-scm.com/downloads/guis) (we recommend [GitKraken](https://www.gitkraken.com)).

You also need [Docker desktop](https://www.docker.com/) installed to run this API dockerized. Docker will run this API on the Common Gateway on dockerized containers so you dont have to worry about having the correct PHP version or other languages/dependencies.

- On the GitHub page of this repository press `Code` and copy the `https` link.

If you installed Git without GUI:

- Open a command line interface, for windows you can press `Win+R` and search for `cmd`.
- Execute the command `git clone (link you copied) (directory you want to clone the repository to`, an example: `git clone https://github.com/CommonGateway/PetStoreAPI.git C:\Users\JohnDoe\Projects`.
- Change to that directory with `cd (directory where repository is cloned to)`, an example: `cd C:\Users\JohnDoe\Projects\PetStore`.

Skip this if you installed Git wihtout GUI and followed those steps, but if you installed Git with GUI (GitKraken):

- Open GitKraken.
- Select `Clone a repo`.
- Paste your copied repository link and select the preferred directory.
- Open a command line interface, for windows you can press `Win+R` and search for `cmd`.
- Change to the chosen directory with `cd (directory where repository is cloned to)`, an example: `cd C:\Users\JohnDoe\Projects\PetStore`.

- Execute `docker-compose up`
- Wait for containers to finish loading.
- If the php container shows: 'Ready to handle connections' your API is accessible on localhost/api or localhost:80/api.

If there are any issues when loading the containers try to execute: `docker-compose pull` and then try `docker-compose up` again.

// TODO How to make API calls to your API / test it

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

