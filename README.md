# hiring-devops

This is a technical assessment for DevOps engineers looking to join Notarise development team.

# Orientation and instruction

The source code in this [repository](./aws-node-rest-api-with-dynamodb-and-offline/) is generated from this [example](https://www.serverless.com/examples/aws-node-rest-api-with-dynamodb-and-offline).

It is a simple serverless framework application, that provisions a TODO application programming interface(API) on Amazon Web Services(AWS). You may modify the source respository to include anything you will like to have, (e.g tests, configuration for additional toolings)

## Pre-requisites

You will need the following installed:

- NodeJS
- Node Package Manager(npm)
- Serverless Framework(sls)

You will also need the following accounts:

- github.com

## Guiding principals

In this team, we value the following, and will lookout for implementations that adhere to these principals, therefore solutions that encompasses these principals will be highly valued and preferred.

### Everything as code over manual processes

Allows for us to share knowledge and better understanding of our environments, this way all changes are version controlled, and have better consistency in deploying across environments.

### Developer centric solutions

Developers comes first, this means we don't pick a technology and find ways to use it for developers, but think of what problems developers have, and find technologies that best fit the problem. This also means that tools we choose need to be developer friendly, and not become a chore to use.

### Low maintenance and making ourselves useless

As much as possible we want to make machines do the work, but we don't want to spend more time maintaining these machines. So services that help to reduce/remove maintenance effort is preferred so that we can spend our time on more valuable work.

###

## Task Overview

There are 4 tasks that you need to complete. The section on developer environment is a bonus section if you will like to push yourself. There is no time limit on this, feel free to modify your setup up till the interview session.

| Task                         | Weightage |
| ---------------------------- | --------- |
| Pipeline                     | 20%       |
| Good Practices               | 35%       |
| Securing the infrastructure  | 35%       |
| Documentation                | 10%       |
| Developer Environment(Bonus) | 20%       |

## Getting started

1. Create your own repository on github and clone it to your machine
2. Initialise serverless repository following these [instructions](https://www.serverless.com/examples/aws-node-rest-api-with-dynamodb-and-offline)
3. Make changes according to the tasks
4. Push your changes to your repository

### Pipeline

#### Context
Automation is key in DevOps to continuously deliver value, so we will need to create a CICD pipeline for this repository, so changes are tested, and packaged for deployments. Since we will not be deploying to an actual AWS account, you may stop just short of it.

#### Task

Create a pipeline that results in:

1. A cloudformation template built

The following should be exposed as github artifacts:

1. cloudformation template
2. zip file of the lambda function

#### Deliverable

A link to view the pipeline, and view the configuration you have created

### Good Practices

#### Context

While build/test/release process of the pipeline is simple to start, typically each stage can be extended to help us save time in various engineering efforts, such as shifting left in security and providing feedback to developers earlier on code smells etc. As much as possible we want to use tools to automate, and only rely on developer intervention when needed.

#### Task

Where appropriate, select and implement tools in your pipeline that can help to perform security scanning and updates. You will be asked to explain how you decided on these tools. When in doubt, refer to the [guiding principals](#guiding-principals)

#### Deliverable

A demo during interview to see the dashboards/output of the various toolings if it is a private page, otherwise a link for us to view the output, and configurations

### Securing the infrastructure

#### Context

Security is paramount, and threats are never ending. We need to think how we can implement security that can provide us with the most defense with the least amount of work for us.

#### Task

Make use of AWS services to secure this API

#### Deliverable

Implement the configuration of these services inside `serverless.yml` so that the deployed function will automatically provision it and add it to the API.

### Documentation

#### Context

Now that you designed and implemented the workflow for this repository, it is time to help others understand what you did, so that others may do the same! Also, this will be helpful to onboard new joiners(consider us interviews as new joiners :D)

#### Task

Write a README.md in the root folder that contains instructions on how to operate in this repository. The README should be as concise as possible while enabling anyone new to get started as quickly as possible

### Developer Environment (Bonus)

#### Context

For developers to work on this repository, they will be starting up some services and running some commands. We can help to make this experience better for local development, by reducing the number of external dependencies, such as requiring a actual dynamodb instance on a AWS account etc.

#### Task

1. Make the function deployable locally without relying on actual infrastructure
2. Configure `package.json` so that `npm run start` will startup everything that is needed to start developing function locally

