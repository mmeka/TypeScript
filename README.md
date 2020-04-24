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
var num2:string = "string"; (redundant; not recommended)
let num3: {
  flag:boolean;
  arr:any[]; // only array of something
  anyVar: any;  // no benefits
  tupleVar: [number, string]; // Tuple is a fixed-length array; heterogenous
};
const num2 = 990; //for constants, typescript won't infer types since values don't change
enum Role {
  ADMIN="admin",SUPERVISOR=190
}
// Union types. see below. Use in case when two types are applicable. Use typeof operator inside function
function fun(arg1 number|string, arg2 'possible value 1'|'possible value 2') {// arg2 has only two possible valid values
}
// Aliases for union types
type alias1 = 'possible value 1' | 'possible value 2';
type alias1 = string | number;
// Declaring variables of function type
let functionVariable:(n: number, s:string) => void
That means, the above variable can only hold the references to function defining of below function
function fun(num1: number, str: string):void {}
// Function that takes a callback function as an argument
function fun2(date:Date, cb:()=>void):date{}


typecasting
coersion

# Project
> npm init (from the project)
> npm install --save-dev lite-server (then under script, add "server": "lite-server")
> npm start (no need to restarts server to pickup changes. As soon as TypeScript complies, changes reflect. Have index.html.)
<script src="JS_file_name" defer></script> (browsers can't understand TypeScript)

# Questions
What are the usecases for Tuple?
How to handle JSON and XML objects returned as response?
How to handle date types and handle dates, times and timezones?
