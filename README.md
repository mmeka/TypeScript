# TypeScript

# Installation, upgrading, managing versions, uninstalling
npm install -g typescript

# Tools
https://www.typescriptlang.org/play/index.html (playground)
Visual Studio Code
Themes, Path intellisense (better support for imports), prettier, ESLint (code quality; TSLint will be merged to ESLint), npm (egamma), Git History (Don Jayammane), Material Icon Theme (to display file icons), Live-server

# Compliation, execution
A corresponding JS file is generated or updated even if the TS file doesn't compile well. noEmitOnError option prevents this.
In real-world projects, "tsc" is added as local Dev dependency.
> tsc <typescript_file_name>
> tsc -w <typescript_file_name> (this will watch for any changes to TS file and compiles to JS file. Watch mode will be on, so use a different terminal window)
> tsc --init (this will tell that the current project is managed by TypeScript. It watches for any changes to TS files and generates JS files with command "tsc -w". Creates tsconfig.json file)
Compilation: converting source code to byte code
Transpilation: conversion of soure code from one language to another

# TSConfig.json
"exclude":["node_modules", <all_JS_files_to_exclude_from_compilation>]. If "excludes" not present, by default node_modules is excluded. Can specify folders or wild cards.
"include" can specify folders that to be included.
"files" only individual files to be included.
"target" default goes to es3
"lib": {"dom","es6","dom.ierable","scripthost"} // default setup when you comment lib:[]
"sourcemap":true // This option generates ".js.map" files, which help in showing up TS files in chrome dev tools for debugging.
"rootdir":"./src"
"outdir":"./dist"   // option to redirect compiled JS files to different folder. "dist" folder will replicate the same structure as in "src" folder.

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
// Unknown type. Any value of any type can be assigned and re-assigned for a variable of 'unknown' type. But, in order to have that variable value to be assigned to some other type variable, an explicit type checking block like "typeof var==='string'" is required. This is better than "any" for this purpose.
let unknownVal:unknown;
// Never return type. When a function returns nothing(see below). Function with an infinite loop also another example.
function fun(errorCode:string,description:string):never{
  throw {"code": errorCode, "desc": description};
}
NOTE: No constructor overloading
typecasting
coersion
Implicit typing - data type will be inferred based on the value assigned to a variable at the time of declaration. No need to explicitly mention the type at that statement.

# Project
> npm init (from the project)
> npm install --save-dev lite-server (then under script, add "server": "lite-server")
> npm start (no need to restarts server to pickup changes. As soon as TypeScript complies, changes reflect. Have index.html.)
<script src="JS_file_name" defer></script> (browsers can't understand TypeScript)

# Third party libraries
If want to include a JavaScript library and if it has definition file (*.d.ts file), then compiler may autocomplete, compile and show errors.

# References
https://www.typescriptlang.org/docs/home.html (documentation)
https://github.com/Microsoft/TypeScript/wiki/Roadmap (roadmap)
https://www.typescriptlang.org/docs/handbook/compiler-options.html(Compiler options)
https://www.youtube.com/channel/UCRQhZGXC0WK85YRXl7nGX0w/playlists (Javascript)
https://www.youtube.com/playlist?list=PLqq-6Pq4lTTanfgsbnFzfWUhhAz3tIezU (basics)
https://youtu.be/BwuLxPH8IDs?t=9405 (datatypes and tsconfig.json)
Manning's TypeScript Quickly book

# Questions
What are the usecases for Tuple?
How to handle JSON and XML objects returned as response?
How to handle date types and handle dates, times and timezones?
tsconfig.json. find defaults and more on it
How the classes, classes with generics, interfaces converted when compiled to JavaScript
Is method overloading supported?
Any limitations on defining constructors?
