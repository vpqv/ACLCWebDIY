# ACLCWebDIY

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 8.3.17.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Deploy to Heroku
* under your project, run `npm i --S express path ng2-ace-editor`
* in `package.json`, perform the following:
    * move everthing in `devDependencies` to `dependencies`
    * under `scripts`, change the start command to `"start": "node server.js"`
    * under `scripts`, add `"postinstall": "ng build --prod"`
* create `server.js` under the root of your project and copy the following into the file:

        const path = require('path');
        const express = require('express');
        const app = express();

        // Serve static files
        app.use(express.static(__dirname + '/dist/<YOUR_PROJECT_NAME>'));

        // Send all requests to index.html
        app.get('/*', function(req, res) {
        res.sendFile(path.join(__dirname + '/dist/<YOUR_PROJECT_NAME>/index.html'));
        });

        // default Heroku port
        app.listen(process.env.PORT || 8080);

* change `<YOUR_PROJECT_NAME>` to the actual name of your project.
* under the root of your project, create `Profile` file and add `web: node server.js` in it.
* push all your changes back to the remote repository.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
