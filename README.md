# COMEM+ Travel Log API

A sample API to develop a mobile application.
Test

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE.txt)

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [Usage](#usage)
  - [Requirements](#requirements)
  - [First-time setup](#first-time-setup)
  - [Run the server in development mode with live reload](#run-the-server-in-development-mode-with-live-reload)
  - [Run the server in production mode](#run-the-server-in-production-mode)
  - [Deploy on Render](#deploy-on-render)
- [Configuration](#configuration)
- [Scripts](#scripts)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Usage

### Requirements

- [Node.js][node] 10.14+
- A running [MongoDB][mongodb] 3.2+ database (see the [Configuration](#configuration) section)

### First-time setup

Clone this repository:

```bash
git clone git@gitlab.com:sysin/comem-travel-log-api.git
```

Install dependencies:

```bash
cd comem-travel-log-api
npm ci
```

### Run the server in development mode with live reload

```bash
npm run dev
```

### Run the server in production mode

```bash
NODE_ENV=production npm start
```

## Deploy on Render

### Fork the project

Start by forking this repository. This will create a copy of the project on which you will have complete admin privileges.

You can fork by pressing the "fork" button at the top left of this page, or by clicking [this link][fork].

### Create a Render Web Service

Follow the instructions in the [Deploy the application to Render][render-deploy-guide] guide.

## Configuration

The following environment variables can be used to customize the server:

| Environment Variable                                         | Default Value                              | Description                                                                                                                                  |
| :----------------------------------------------------------- | :----------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------- |
| `BASE_URL`                                                   | `http://localhost:<PORT>`                  | The base URL at which the API is deployed.                                                                                                   |
| `BCRYPT_COST`                                                | `10`                                       | [bcrypt][bcrypt] cost factor.                                                                                                                |
| `DATABASE_NAME`                                              |                                            | The name of the database                                                                                                                     |
| `DATABASE_URI`, `DATABASE_URL`, `MONGODB_URI`, `MONGODB_URL` | `mongodb://localhost/comem-travel-log-api` | The URL used to connect to the database. The 4 variables are listed from highest to lowest precedence.                                       |
| `DOCS_BROWSER`                                               |                                            | _Development option:_ which browser application to open the API documentation in.                                                            |
| `DOCS_OPEN`                                                  | `true`                                     | _Development option:_ whether to open the API documentation in the browser automatically when running `npm run dev` or `npm run docs:serve`. |
| `DOCS_PORT`                                                  | _Random port_                              | _Development option:_ port on which to serve the API documentation when running `npm run dev` or `npm run docs:serve`.                       |
| `LOG_LEVEL`                                                  | `info`                                     | Log verbosity. Available levels are: `trace`, `debug`, `info`, `warn`, `error`, `fatal`.                                                     |
| `PORT`                                                       | `3000`                                     | Port (or pipe) to bind the server to.                                                                                                        |
| `SECRET`                                                     |                                            | Secret used to sign [JWT][jwt] tokens.                                                                                                       |

Since [dotenv][dotenv] is used, you can also set these variables using a `.env` file:

```
PORT=4000
SECRET=changeme
```

## Scripts

The following scripts can be used to perform useful tasks:

| Script               | Description                                                                                                                 |
| :------------------- | :-------------------------------------------------------------------------------------------------------------------------- |
| `npm run dev`        | Build the API documentation, start the server in development mode with live reload and watch the documentation for changes. |
| `npm run docs:build` | Build the API documentation. (Run by `npm run dev` and after `npm install`.)                                                |
| `npm run docs:clean` | Erase the API documentation. (Run by `npm run dev`.)                                                                        |
| `npm run docs:serve` | Serve the API documentation on a local port with live reload, optionally open a browser. (Run by `npm run dev`.)            |
| `npm run docs:watch` | Watch the source code for changes to automatically rebuild the API documentation. (Run by `npm run dev`.)                   |
| `npm run doctoc`     | Regenerate this README's table of contents.                                                                                 |
| `npm start`          | Start the server without live reload.                                                                                       |
| `npm run start:dev`  | Start the server with live reload.                                                                                          |

[bcrypt]: https://en.wikipedia.org/wiki/Bcrypt
[dotenv]: https://www.npmjs.com/package/dotenv
[fork]: https://github.com/MediaComem/comem-travel-log-api/fork
[jwt]: https://jwt.io
[mongodb]: https://www.mongodb.com
[mongodb-atlas-guide]: https://github.com/MediaComem/comem-archioweb/blob/main/guides/deploy-in-the-cloud.md#create-a-mongodb-cluster-on-mongodb-atlas
[node]: https://nodejs.org/
[render-deploy-guide]: guides/deploy.md
