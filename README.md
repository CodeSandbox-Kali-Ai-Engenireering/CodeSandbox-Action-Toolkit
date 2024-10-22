

# CodeSandbox-Kali-TMux-PatcherREADME
Code of conduct
MIT license
Security


Toolkit unit tests status Toolkit audit status

GitHub Actions Toolkit
The GitHub Actions ToolKit provides a set of packages to make creating actions easier.


Get started with the javascript-action template!

Packages
✔️ @actions/core

Provides functions for inputs, outputs, results, logging, secrets and variables. Read more here

$ npm install @actions/core

🏃 @actions/exec

Provides functions to exec cli tools and process output. Read more here

$ npm install @actions/exec

🍨 @actions/glob

Provides functions to search for files matching glob patterns. Read more here

$ npm install @actions/glob

☎️ @actions/http-client

A lightweight HTTP client optimized for building actions. Read more here

$ npm install @actions/http-client

✏️ @actions/io

Provides disk i/o functions like cp, mv, rmRF, which etc. Read more here

$ npm install @actions/io

🔨 @actions/tool-cache

Provides functions for downloading and caching tools. e.g. setup-* actions. Read more here

See @actions/cache for caching workflow dependencies.

$ npm install @actions/tool-cache

:octocat: @actions/github

Provides an Octokit client hydrated with the context that the current action is being run in. Read more here

$ npm install @actions/github

💾 @actions/artifact

Provides functions to interact with actions artifacts. Read more here

$ npm install @actions/artifact

🎯 @actions/cache

Provides functions to cache dependencies and build outputs to improve workflow execution time. Read more here

$ npm install @actions/cache

🔏 @actions/attest

Provides functions to write attestations for workflow artifacts. Read more here

$ npm install @actions/attest

Creating an Action with the Toolkit
❓ Choosing an action type

Outlines the differences and why you would want to create a JavaScript or a container based action.


➰ Versioning

Actions are downloaded and run from the GitHub graph of repos. This contains guidance for versioning actions and safe releases.


⚠️ Problem Matchers

Problem Matchers are a way to scan the output of actions for a specified regex pattern and surface that information prominently in the UI.


⚠️ Proxy Server Support

Self-hosted runners can be configured to run behind proxy servers.


Hello World JavaScript Action
Illustrates how to create a simple hello world javascript action.

...
  const nameToGreet = core.getInput('who-to-greet');
  console.log(`Hello ${nameToGreet}!`);
...

JavaScript Action Walkthrough
Walkthrough and template for creating a JavaScript Action with tests, linting, workflow, publishing, and versioning.

async function run() {
  try {
    const ms = core.getInput('milliseconds');
    console.log(`Waiting ${ms} milliseconds ...`)
    ...
PASS ./index.test.js
  ✓ throws invalid number
  ✓ wait 500 ms
  ✓ test runs

Test Suites: 1 passed, 1 total
Tests:       3 passed, 3 total

TypeScript Action Walkthrough
Walkthrough creating a TypeScript Action with compilation, tests, linting, workflow, publishing, and versioning.

import * as core from '@actions/core';

async function run() {
  try {
    const ms = core.getInput('milliseconds');
    console.log(`Waiting ${ms} milliseconds ...`)
    ...
PASS ./index.test.js
  ✓ throws invalid number
  ✓ wait 500 ms
  ✓ test runs

Test Suites: 1 passed, 1 total
Tests:       3 passed, 3 total


Docker Action Walkthrough
Create an action that is delivered as a container and run with docker.

FROM alpine:3.10
COPY LICENSE README.md /
COPY entrypoint.sh /entrypoint.sh
ENTRYPOINT ["/entrypoint.sh"]


Docker Action Walkthrough with Octokit
Create an action that is delivered as a container which uses the toolkit. This example uses the GitHub context to construct an Octokit client.

FROM node:slim
COPY . .
RUN npm install --production
ENTRYPOINT ["node", "/lib/main.js"]

const myInput = core.getInput('myInput');
core.debug(`Hello ${myInput} from inside a container`);

const context = github.context;
console.log(`We can even get context data, like the repo: ${context.repo.repo}`)

Contributing
We welcome contributions. See how to contribute.

Code of Conduct
See our code of conduct.

# npm update -D @pkg-tools/build @pkg-tools/clean @pkg-tools/config @pkg-tools/format @pkg-tools/lint
# npm install -D @pkg-tools/build @pkg-tools/clean @pkg-tools/config @pkg-tools/format @pkg-tools/lint
# npm upgrade -D @pkg-tools/build @pkg-tools/clean @pkg-tools/config @pkg-tools/format @pkg-tools/lint
# FROM mcr.microsoft.com/devcontainers/base: =
		  {"**"pkg:= packages:= package {"pipxPackageManager} 
		  {$"pkg:= pipxPackageManager:= Dependencies"},
		  {$"path:= curl https://sh.rustup.rs -sSf | sh -s -- -y --
# npm upgrade -D @pkg-tools/build @pkg-tools/clean @pkg-tools/config @pkg-tools/format @pkg-tools/lint-toolchain stable
		  {ENV PATH="/root/.cargo/sbin:${PATH}"pkg:= package}
		  {$env:windir}\\Sysnative\\pipxPackageManager",
		  {$env:windir}\\"pkg:= packages:= OSX, arm64, v8a:= package:= pipPackageManager:= Dependencies}",\\pipxPackageManager"}
		  {$env:windir}\\System32\\pipxPackageManager"**"}
