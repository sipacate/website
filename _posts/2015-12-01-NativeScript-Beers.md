---
layout:     post
title:      "NativeScript Beers"
subtitle:   "A tutorial"
author:     "horacio"
---


**NativeScript Beers** is a tutorial of the [Beer Tutorials](http://www.beer-tutorials.org) series.
In this tutorial we will create a simple app that queries a beer catalog and displays a list of beers.

## Getting Started

Install [NodeJS](https://nodejs.org/) and then using the node package manager (npm), install native script.

```
npm install -g nativescript
```

After installing native script, create a new project called `nativescript-beers`.

```
tns create nativescript-beers
```

Navigate to the project directory and add the mobile development platform.

```
tns platform add android
```

Run the application on the Android emulator.

```
tns run android --emulator
```

> Note: To run the application in the Android emulator, you need to have the Android SDK
> installed and configured on your computer.
> The easiest way to do it is to install [Android Studio](http://developer.android.com/tools/studio/index.html)
> for your platform.

![Initial app](../img/2015-12-01-initial-app.png)

## Project Structures


    .
    └── nativescript-beers
        ├── app
        │   ├── App_Resources
        │   │   ├── Android
        │   │   └── iOS
        │   ├──  main-page.js
        │   ├──  main-page.xml  
        │   ├──  main-view-model.js  
        │   ├──  package.json  
        │   ├──  references.d.ts
        │   ├── app.css
        │   ├── app.js
        │   └── ...
        ├── node_modules
        │   └── tns-core-modules
        ├── package.json
        └── platforms
            ├── android
            └── ios    


Inside  the project folder there are 3 sub-folders: `app`, `lib` and `platforms`. The application source code resides in the `app` folder. Application code is written using JavaScript and the user interface designed using XML.

Inside the `app` folder is a file called `main-page.xml` which has the default user interface code. In `main-view-model.js` is the default model code and` main-page.js` defines the application logic. Finally `app.js` contains the code to start the application with the defined modules.


## Designing the app

Let’s start by designing the application using XML. Open `main-page.xml` and look at the default code. Remove everything except the `Page` tag. The `Page` tag has an attribute called `loaded` which executes the `pageLoaded` function once the app loads. The `pageLoaded` function is inside the `main-page.js` file.

This project will use a *stack layout* to design our app. There are [a number of layouts offered by native script](http://docs.nativescript.org/layouts).
