# Development Workflow
> Includes information to on how to make changes to the project and what process to follow to get the changes commited.

Table of Contents
=================
* [Running Locally](#running-locally)
* [Branch Management](#branch-management)
* [Making Changes](#making-changes)
* [Testing Strategy](#testing-strategy)
* [Jira Workflow](#jira-workflow)

Running Locally
===============
> Indicates how to run the solution locally once the developer machine setup is complete and the repo has been cloned.

**Example**
1. Open a command prompt window and run `npm run dotnet`
2. Open another command prompt window and run `npm run webpack`

Branch Management
=================
> Indicates the process that should be followed when new development begins in terms of how git branches should be created and merged.

**Example**
1. At the beginning of each sprint created a new feature branch using the following schema: `feature/yyyy-mm-dd-[yourLastName]`
2. On the tuesday before a sprint ends merge your feature branch into the `development` branch.

Making Changes
==============
> Includes steps that should be followed as changes are made to the project. If the project has a different process based on where changes are being made, those should be broken out as sub-sections.

**Example**
1. Be sure to make new changes in the current sprint feature branch.
2. When developing a new API endpoint be sure to create integration tests for 75% code coverage.
3. Run the entire test suite prior to pushing any commits (see testing document for details on running tests).

Testing Strategy
================
> Details the various types of automated testing that the project makes use of (e.g. unit, integration, functional).

**Example**
This project uses xUnit, Moq, and Shouldly for writing and running unit and integration tests. Functional testing is on the roadmap, but has not yet been put into practice. All testing projects are included in the `Tests` solution folder. THe testing project names mirror the project they are responsible for testing (e.g. `Business.Conductors.Tests`).

### Unit
> Includes the details of the unit testing strategy. What should have unit tests and/or what shouldn't.

**Example**
All functions in the `Business.Conductors` project should have 75% code coverage. Unit tests are written in the `Business.Conductors.Tests` project. Each conductor has its own corresponding test class.

### Integration
> Includes the details of the integration testing strategy. What should have unit tests and/or what shouldn't.

**Example**
All Web API controllers in the `Presentation.Web` project should have 75% code coverage. Integration tests are written in the `Presentation.Web.Tests` project. Each Web API controller has its own corresponding test class.

### Functional
> Includes the details of the integration testing strategy. What should have unit tests and/or what shouldn't.

**Example**
Functional testing is on the roadmap, but has not yet been implemented at this time.

Feature Management (link out to branch strategy)
=============
> What is this?  What should it link out to?

Jira Workflow
=============
> Includes details of how user stories and chores get assigned to a sprint, and how they are managed throughout the build, test and deployment phases.

**Example**
1. Every Tuesday during sprint planning the user stories are reviewed to ensure all requirements are known. Any adjustments to estimates are made at this time. Estimates are story points using the Fibonacci scale (0, 1, 2, 3, 5, 8, 13, 21). Stories are then assigned to a developer and moved into the upcoming sprint.
2. Sprints begin Wednesday morning. When a developer begins development of a user story they should change the status to `development started`
3. When development is ready to be moved to the `working` environment for testing the developer should change the status to `pending QA`.
4. The developer in charge of deployments to `working` will deploy all user stories in the `pending QA` to the `working` environment. Once the deployment has successfully completed the developer will update the status of _all_ deployed stories to `delivered` and assign them to the QA engineer.
5. When the QA engineer begins testing a user story they will update the status to `testing`
6. If a user story passes QA the status is set to `accepted` and is assigned to the developer in charge of production deployments. If the story fails QA the status is set to `rejected` and is assigned to the developer who delivered the story.
7. Once all user stories have been accepted the deployment engineer will deploy the features to the production environment. Once the deployment is successfully completed the status of all accepted user stories is set to `completed in production` and are assigned to the product manager.