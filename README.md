__Main branch__ - [![run-cypress-tests](https://github.com/hrmeetsingh/cypress-github-custom-actions/actions/workflows/main.yml/badge.svg?branch=main)](https://github.com/hrmeetsingh/cypress-github-custom-actions/actions/workflows/main.yml)

__Docker branch__ - [![run-cypress-tests](https://github.com/hrmeetsingh/cypress-github-custom-actions/actions/workflows/main.yml/badge.svg?branch=docker-branch)](https://github.com/hrmeetsingh/cypress-github-custom-actions/actions/workflows/main.yml)


# cypress-github-custom-actions

This is sample repo to verify running a custom github action using docker 
Example of test used from [Page Dom testing - Cypress recipes](https://github.com/cypress-io/cypress-example-recipes/tree/master/examples/testing-dom__page-source)

This repo has a manually triggered workflow
- Run on "main" branch for cypress provided github action
- Run on "docker-branch" branch for using cypress included image container and custom action
- Run on "run-and-report" branch for using mochawesome reports published on [GH Pages Report](https://hrmeetsingh.github.io/cypress-github-custom-actions/)