# Front-end Development Principles
... 

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
