# Express.JS
Fast, unopinionated, minimalist web framework for Node.js

## Installing
Assuming you’ve already installed Node.js, create a directory to hold your application, and make that your working directory.

```bash
mkdir myapp
cd myapp
```
Use the npm init command to create a package.json file for your application.
```bash
npm init
```
This command prompts you for a number of things, such as the name and version of your application. For now, you can simply hit RETURN to accept the defaults for most of them, with the following exception:
```bash
entry point: (index.js)
```
Enter app.js, or whatever you want the name of the main file to be. If you want it to be index.js, hit RETURN to accept the suggested default file name.

Now install Express in the myapp directory and save it in the dependencies list. For example:
```bash
npm install express --save
```
# Getting Started
Now I have created `index.js` and copy template to it, for an express app from here & make changes according to requirement:
```js
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening at http://localhost:${port}`)
})
```

## Serving & Routing files Statically
Now I created new folder `routes` & created new file `blog.js`, in which requests will be taken and respective responses will be given. Serve CSS and JS related to front-end in a folder `static`.

# Express Handlebars
A Handlebars view engine for Express which doesn't suck.

## Installation
Install using npm:
```bash
npm install express-handlebars
```

## Usage
This view engine uses sensible defaults that leverage the "Express-way" of structuring an app's views. This makes it trivial to use in basic apps:

### Basic Usage

#### Directory Structure:
```bash
.
├── app.js
└── views
    ├── home.handlebars
    └── layouts
        └── main.handlebars

2 directories, 3 files
```
#### app.js:
Creates a super simple Express app which shows the basic way to register a Handlebars view engine using this package.
```js
var express = require('express');
var exphbs  = require('express-handlebars');

var app = express();

app.engine('handlebars', exphbs());
app.set('view engine', 'handlebars');

app.get('/', function (req, res) {
    res.render('home');
});

app.listen(3000);

```