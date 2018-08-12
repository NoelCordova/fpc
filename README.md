# Firebase Personal Cloud

*Firebase personal cloud* (**_FPC_**) is a repository where i store my source code for my personal cloud hosted on [Firebase](https://firebase.google.com/ "Firebase Homepage") and it can be applied into another new project.

<br>

## Table of Contents
* [Instructions (Angular)](https://github.com/NoelCordova/fpc#instructions-for-a-new-project-angular)
  * [Install Angular CLI](https://github.com/NoelCordova/fpc#install-angular-cli)
  * [Create Angular Project](https://github.com/NoelCordova/fpc#create-an-angular-project)
  * [Install Firebase CLI](https://github.com/NoelCordova/fpc#install-firebase-cli)
  * [Firebase login](https://github.com/NoelCordova/fpc#login-firebase)
  * [Link Firebase into Angular](https://github.com/NoelCordova/fpc#link-firebase-into-angular)
  * [Deploying](https://github.com/NoelCordova/fpc#deploying)

<br>

## Instructions for a new project (**_Angular_**)

### Install angular CLI
```
npm install -g @angular/cli
```
---
### Create an Angular project
```
ng new APP_NAME
```
---
### Install Firebase CLI
```
npm install -g firebase-tools
```
---
### Login Firebase
```
firebase login
```

*example*
```
$ firebase login
? Allow Firebase to collect anonymous CLI usage and error reporting information? No

Visit this URL on any device to log in:
https://SOME_URL/

Waiting for authentication...

+  Success! Logged in as USER_EMAIL@gmail.com
```
---
### Link Firebase into Angular
```
firebase init
```

*example*
* **DIST_FOLDER:** For Angular applications select **_dist_**
```
$ firebase init

     ######## #### ########  ######## ########     ###     ######  ########
     ##        ##  ##     ## ##       ##     ##  ##   ##  ##       ##
     ######    ##  ########  ######   ########  #########  ######  ######
     ##        ##  ##    ##  ##       ##     ## ##     ##       ## ##
     ##       #### ##     ## ######## ########  ##     ##  ######  ########

You're about to initialize a Firebase project in this directory:

  DIRECTORY_PATH/DIRECTORY_NAME

? Are you ready to proceed? Yes
? Which Firebase CLI features do you want to setup for this folder? Press Space to select features, then Enter to confirm your choices. Hosting: Configure and
deploy Firebase Hosting sites

=== Project Setup

First, let's associate this project directory with a Firebase project.
You can create multiple project aliases by running firebase use --add,
but for now we'll just set up a default project.

? Select a default Firebase project for this directory: FIREBASE_PROJECT_NAME

=== Hosting Setup

Your public directory is the folder (relative to your project directory) that
will contain Hosting assets to be uploaded with firebase deploy. If you
have a build process for your assets, use your build's output directory.

? What do you want to use as your public directory? DIST_FOLDER
? Configure as a single-page app (rewrite all urls to /index.html)? Yes
+  Wrote dist/index.html

i  Writing configuration info to firebase.json...
i  Writing project information to .firebaserc...

+  Firebase initialization complete!
```
---
### Deploying

```
npm run deploy
```
*example*
```
$ npm run deploy

> PACKAGE_NAME@VERSION deploy DIRECTORY_PATH/DIRECTORY_NAME
> ng build --output-path dist --prod && firebase deploy


Date: 2018-08-11T17:25:06.839Z
Hash: 2d4406b13b297a4b7774
Time: 23780ms
chunk {0} runtime.a66f828dca56eeb90e02.js (runtime) 1.05 kB [entry] [rendered]
chunk {1} styles.34c57ab7888ec1573f9c.css (styles) 0 bytes [initial] [rendered]
chunk {2} polyfills.2f4a59095805af02bd79.js (polyfills) 59.6 kB [initial] [rendered]
chunk {3} main.8a82c37dbab110767431.js (main) 172 kB [initial] [rendered]

=== Deploying to 'FIREBASE_PROJECT_NAME'...

i  deploying hosting
i  hosting: preparing dist directory for upload...
+  hosting: 7 files uploaded successfully

+  Deploy complete!

Project Console: ...
Hosting URL: PROJECT_URL
```

##### Custom script:
On the **_package.json_** file there's a script called `deploy` with these commands:

*Angular build on dist folder*
```
ng build --output-path dist --prod
```

*Deploy to firebase*
```
firebase deploy
```