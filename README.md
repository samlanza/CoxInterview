# CoxInterview
Parsing app for Cox interview

# Generate Performance Users in Bulk

## Prerequisites

- [NodeJS](https://nodejs.org/en/download/)

  ## Installation

**Install dependencies**

Clone the generated repository on your local machine, move to the project root folder and install the dependencies defined in [`package.json`](./package.json)

```bash
npm install
```

## Transpiling from TypeScript to JavaScript

We first have to transpile the TypeScript code into JavaScript.

```bash
npm run compile
```

This command transpiles the TypeScript to Javascript and stores it in the `./dist` folder.

## Get a Token from OIDC Management UI

You'll have to obtain your user token from the OIDC Management UI.  I was able to grab it from Fiddler.  Look for the `generate-perf-users.ts` file in this project.  That is the entry point.  Paste in the token you copied from OIDC Management UI.

## Generate Performance Users

Modify the `generatePerfUsers(...)` method in `generate-perf-users.ts` with the following arguments:

1) token
2) the name of your test user
3) description of the test user
4) role
5) number of users you want to create
6) *OPTIONAL* starting number (NOTE:  This will default to 1 if you don't provide it.  This indicates the number you want the index of the user to start with).

## Run It

```bash
node dist/generate-perf-users.js
```
The users created are then added to a file called `users-unique.csv` under `./dist/src/helpers`.

