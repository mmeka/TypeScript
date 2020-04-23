# TypeScript

# Installation, upgrading, managing versions, uninstalling
npm install -g typescript

# Visual studio code setup
Themes, Path intellisense (better support for imports), prettier, ESLint (code quality; TSLint will be merged to ESLint), npm (egamma), Git History (Don Jayammane), Material Icon Theme (to display file icons), Live-server

# Compliation, execution

# Debugging

# Data types
JavaScript - number, string, boolean, null and undefined
TypeScript - number, string, boolean, any, null, undefined, Array, object

Typescript is statically typed.

variable: type (but, compiled JavaScript file doesn't have those data types)
let num1 = 5; (Typescript can infer)
var num2:number = 9.0; (redundant; not recommended)
const num3: {
  flag:boolean;
  arr:string[];
  anyVar: any;  // no benefits
};

typecasting
coersion

# Project
> npm init (from the project)
> npm install --save-dev lite-server (then under script, add "server": "lite-server")
> npm start (no need to restarts server to pickup changes. As soon as TypeScript complies, changes reflect. Have index.html.)
<script src="JS_file_name" defer></script> (browsers can't understand TypeScript)
