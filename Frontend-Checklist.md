# Front-end Development Principles

#### Front-end
* Redux Hooks https://react-redux.js.org/api/hooks 
* https://reactjs.org/docs/hooks-intro.html

## JS Testing & Tools
* https://github.com/slikts/tooling/
* https://github.com/typescript-cheatsheets/react-typescript-cheatsheet
 
## Requirements and best practices
* All the UI should be built mobile first
* Use SVG instead of png or jpg whenever possible
* Use SASS for building CSS http://sass-lang.com/guide
  - Review UI kits styles before adding new ones

## Reactjs / Redux
* Know your components. Read the entire source code
* Minimize external dependences
* Fail gracefully. Components should be resistant to various props scenarios
* *Don’t understand, ask* Review Components with colleagues before refactoring

## Javascript code style and linter
* Use ESlint and [Prettier](https://github.com/prettier/prettier) for enforcing the style guide 
* Use Gitlab CI for build process ( running lints and test units )
* All lint issues should be resolved before code review

## Personal Staging
Use Dokku, Docker-powered PaaS https://github.com/dokku/dokku

## BACK-END NODEJS TESTING

* SuperTest
https://mochajs.org/

* Chai is a BDD / TDD assertion library for node and the browser that can be delightfully paired with any javascript testing framework
https://www.chaijs.com/

* nock - HTTP server mocking and expectations library for Node.js
https://github.com/nock/nock

* Promise based HTTP client for the browser and node.js
https://github.com/axios/axios

* SuperTest
https://github.com/visionmedia/supertest

* Sinon.JS - Standalone test spies, stubs and mocks for JavaScript. Works with any unit testing framework.
https://sinonjs.org/