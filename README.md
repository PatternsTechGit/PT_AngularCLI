
# Muti Page Application Vs Single Page Application

In a traditional Web app (MPA), every time the app calls the server, the server renders a new HTML page. This triggers a page refresh in the browser everytime.

whereas, In an SPA, after the first page loads, all interaction with the server happens through AJAX calls. These AJAX calls return data usually in JSON format. The app uses the JSON data to update the page dynamically, without reloading the full page.

The below figures represents the two approaches.


![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

#

# Angular CLI
Angular Command-Line Interface (CLI) is a tool to initialize, develop, scaffold, and maintain Angular applications directly from a command shell.


## Installation

- Install the [npm package manager](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) :
- Then enter the following command into command prompt.
```Installing Angular CLI
  npm install -g @angular/cli
```

## Scaffolding Angular Application
To create a new project run the following command on command prompt:

```Generating new Angular Application
  ng new BBBankUI
```
Use the following commands to go into the parent directory of your newly created project "BBBankUI" and run the application

```Generating new Angular Application
  cd BBBankUI
  ng serve
```
In your browser, open http://localhost:4200/ to see the new application run.


## Some useful Angular CLI Commands
One of the most important and used angular CLI command is ng [generate](https://angular.io/cli/generate), It has multiple arguments.

One of argument of generate command for a new component is following:

```ng Generate Command
    ng g c first-component
```

Here, g is shorthand property for generate and c is for component.

Learn more about [Angular CLI commands](https://angular.io/cli)

## Angular Project Structure
This is what our project tree looks like:

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

Let's have a look at some of the files and folders:

#### 1. /e2e/
e2e stands for end-to-end and it refers to e2e tests of the website.

#### 2. /node_modules/
All 3rd party libraries are installed into this folder when you run npm install. Those libraries are bundled into our application.


#### 3. /src/
This is where your all of the application source code goes. 

- **/app/**
When you scaffold an angular application your first component is generated here.

- **/environments/**
This folder contains two files, each for different environments. You will use this file to store environment specific configuration like database credentials or server addresses. By default there are two files, one for production and on for development.

- **index.html**
The index.html file is the file used by the angular compiler to render our application inside the browser.

This file loads the root component of the application (AppComponent) by using the selector  (<app-root>):

- **main.ts**
This is the starting point for our app.

#### 4. .gitignore
This file instructs git which files should be ignored when working with git repository. 

#### 5. .package.json
This file is mandatory for every npm project. It contains basic information regarding our project (name, description, license etc.) commands which can be used, dependencies — those are packages required by our application to work correctly, and devDepndencies — again a list of packages which are required for our application however only during the development phase. I.e. we need Angular CLI only during development to build a final package however on production we don't need it anymore.

#### 6. tsconfig.json
A bunch of compiler settings. Based on these settings, it will compile code to JS code which that browser can understand.

#### 7. tslint.json
TSlint is a useful static analysis tool that checks our TypeScript code for readability, maintainability, and functionality errors. This file contains its configuration. We will see how it works in a future lesson.