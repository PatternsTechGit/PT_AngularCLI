# Scaffolding Single Page Application using Angular CLI

## Muti Page Application (MPA) Vs Single Page Application (SPA)

In a traditional Web app (MPA), every time the app calls the server, the server renders a new HTML page. This triggers a page refresh in the browser everytime.

whereas, In an SPA, after the first page loads, all interaction with the server happens through AJAX calls. These AJAX calls return data usually in JSON format. The app uses the JSON data to update the page dynamically, without reloading the full page.

The below figures represents the two approaches.

![SPA vs MPA](https://github.com/PatternsTechGit/PT_AngularCLI/blob/main/images/spa_arch.png)

### Angular CLI
Angular Command-Line Interface (CLI) is a tool to initialize, develop, scaffold, and maintain Angular applications directly from a command shell.

### About this exercise
In this lab we will
- Install Angular CLI
- Scaffold a new Angular Application
- See what does `ng Generate` command do?
- See how an Angular project structure looks like
- The Root module of Angular App
- Entry point of a new Angular App

------------

#### Step 1:  Installing Angular CLI

- Install the [npm package manager](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) :
- Then enter the following command into command prompt.
```Installing Angular CLI
  npm install -g @angular/cli
```

#### Step 2:   Scaffolding Angular Application
To create a new project run the following command on command prompt:

```Typescript
ng new BBBankUI
```
Use the following commands to go into the parent directory of your newly created project "BBBankUI" and run the application

```Typescript
  cd BBBankUI
  npm start
```
In your browser, open http://localhost:4200/ to see the new application run.


#### Step 3:  Some useful Angular CLI Commands
One of the most important and used angular CLI command is ng [generate](https://angular.io/cli/generate), It has multiple arguments.

One of argument of generate command for a new component is following:

```
    ng g c first-component
```

Here, g is shorthand property for generate and c is for component.

Learn more about [Angular CLI commands](https://angular.io/cli)

#### Step 4:  Angular Project Structure
This is what our project tree looks like:

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)

Let's have a look at some of the files and folders:

1. #### /e2e/
e2e stands for end-to-end and it refers to e2e tests of the website.

2. #### /node_modules/
All 3rd party libraries are installed into this folder when you run npm install. Those libraries are bundled into our application.

3.  #### /src/
This is where your all of the application source code goes. 

- **/app/**
When you scaffold an angular application your first component is generated here.

- **/environments/**
This folder contains two files, each for different environments. You will use this file to store environment specific configuration like database credentials or server addresses. By default there are two files, one for production and on for development.

- **index.html**
The index.html file is the file used by the angular compiler to render our application inside the browser.
This file loads the root component of the application (AppComponent) by using the selector  `<app-root>`

- **main.ts**
This is the starting point for our app.

4. #### .gitignore
This file instructs git which files should be ignored when working with git repository. 

5. #### .package.json
This file is mandatory for every npm project. It contains basic information regarding our project (name, description, license etc.) commands which can be used, dependencies — those are packages required by our application to work correctly, and devDepndencies — again a list of packages which are required for our application however only during the development phase. I.e. we need Angular CLI only during development to build a final package however on production we don't need it anymore.

6. #### tsconfig.json
A bunch of compiler settings. Based on these settings, it will compile code to JS code which that browser can understand.

7. #### tslint.json
TSlint is a useful static analysis tool that checks our TypeScript code for readability, maintainability, and functionality errors. This file contains its configuration. We will see how it works in a future lesson.

#
#### Step 5:  How Angular Application is Structured

The Angular application is structured in components and modules.Every Angular application has at least one Module (NgModule class), the root module, which is conventionally named AppModule and resides in a file named app.module.ts . You launch your application by bootstrapping the root NgModule

- [**Module**](https://angular.io/guide/architecture-modules)
Modules can be described as self-contained chunks of the functionality in your application which can run independently. In Angular, Modules are the collection of the Components, Service directives, and Pipes which are related such that they can be combined to form a module

- [**Component**](https://angular.io/api/core/Component)
The most important feature of any Angular application is the component which controls the View or the template that we use. Generally, we write all the application logic for the View that is mapped to this component.

### Module vs Components
The module can be considered as a collection of components, directives, services, pipes, helpers, etc.

Each component can use other components, which are declared in the same module. To use components declared in other modules, they need to be exported from that module and the module needs to be imported into our module where we need that functionality.

![Module vs Component](https://github.com/PatternsTechGit/PT_AngularCLI/blob/main/images/module_vs_component.png)

One of many modules combines up to make an Application.

#### Step 6:  APP MODULE: The Root Module
Defines `AppModule`, the [root module](https://angular.io/guide/bootstrapping) that tells Angular how to assemble the application. By default it declares only the `AppComponent`. Soon there will be more components to declare as your application grows.

![App.module.ts](https://github.com/PatternsTechGit/PT_AngularCLI/blob/main/images/app_module_ts.png)

To use any method define in another classes, we need to import it first. So `import { }` statement helps us to do it.

After the `import` statements, you come to a class adorned with the `@NgModule` [*decorator*.](https://ultimatecourses.com/blog/angular-decorators)

The `@NgModule` decorator identifies `AppModule` as an Angular module class (also called an `NgModule` class). `@NgModule` takes a metadata object that tells Angular how to compile and launch the application.

### The *declarations* array
Declarations are used to declare components, directives, pipes that belongs to the current module. Everything inside declarations knows each other.

### The *imports* array
Imports makes the exported declarations of other modules available in the current module. It is used to import supporting modules likes FormsModule, RouterModule, CommonModule etc.

### The *providers* array
Providers are used to make services and values known to dependency injection. They are added to the root scope and they are injected to other services or directives that have them as dependency.

### The *bootstrap* array
The application launches by bootstrapping the root `AppModule`, which is also referred to as an `entryComponent`. Among other things, the bootstrapping process creates the component(s) listed in the `bootstrap` array and inserts each one into the browser DOM.

#### Step 7:  MAIN.TS: The Entry Point

This file acts as the entry point of the application. This entry point is defined in the internals of webpack that is used by Angular to support the modular functionality. 
Main.ts file calls the function `bootstrapModule(AppModule)` which tells the builder to bootstrap the app

![main_ts.png file](https://github.com/PatternsTechGit/PT_AngularCLI/blob/main/images/main_ts.png)

From the `main.ts` file, it is very clear that we are bootstrapping the app with `AppModule.`
AppModule is imported from the app of the main parent module, and the same is given to the bootstrap Module, which makes the `appmodule` load.
