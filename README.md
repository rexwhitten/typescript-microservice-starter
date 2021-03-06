# TypeScript Microservice Starter

This is an easy boilerplate for building Node.js microservices with TypeScript. Put your typescript code inside `./src` folder and you are ready to go!

## Features

* VS Code debugger configs in .vscode folder
* recommended Dockerfile for secure nodejs container
* tsconfig.json for [typescript compiler](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html)
* strict tslint.json for [tslint](https://palantir.github.io/tslint/)

## Getting Started

```
# Clone the repo
git clone https://github.com/nucleode/typescript-microservice-starter.git
cd typescript-microservice-starter

# Remove reference to the original starter
rm -rf .git && git init && npm init

# Install development dependencies
npm i

# start development server
npm run dev
```

## Included npm scripts

Run this commands from the project folder with `npm run "script-name"`.
* `dev`: runs in development server with [nsp security check](https://nodesecurity.io/), [ts linter](https://palantir.github.io/tslint/) and `nodemon` watching `.ts` files inside `./src` folder and autorestart on save.
* `build`: builds all .ts files from `./src` folder to `./build`
* `lint`: lints source code using `tslint`
* `security-check`: checks installed dependencies against node security database
* `share`: runs development server and expose it with [localtunnel](https://localtunnel.github.io/www/)
* `start`: starts production server. Run `build` command to compile TS to JS before running this.
* `update`: easily check for updates and update all dependencies

## Debugging
> Warning: This starter uses new V8 [inspect protocol](https://nodejs.org/api/debugger.html) so you have to use at least Node.js 7.7.4 if you want to use the included debugger settings.

#### Steps:
* start dev server with `npm run dev`
* now you have two ways:
  * use the provided debug URL in Chrome
  * use VS Code included (inside .vscode folder) `attach` config (best debugging experience)

## Docker Support

This stater uses Node.js best practices and creates dummy user to start node process, instead of using root user.

```
# Go to the root of your repo created from this starter
# Build your docker image
docker build -t my-project-name .

# run your docker container
docker run -p PORT:PORT my-project-name
```
