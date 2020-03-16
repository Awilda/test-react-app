# React From Scratch

## Steps

#### 1. Create project directory

> project-app-folder

> > public

>- index.html

> > src
 
>- components

>- app.js


#### 2. Install [live-server](https://classic.yarnpkg.com/en/package/live-server)
	
> if yarn:
	
	$ yarn global add live-server
> if npm:
	
	$ npm -g live-server


#### 3. Create package.json file

> if yarn:
	
	$ yarn init
> if npm:
	
	$ npm init


#### 4. Install [react](https://classic.yarnpkg.com/en/package/react) & [react-dom](https://classic.yarnpkg.com/en/package/react-dom)

>
	
	$ yarn add react react-dom


#### 5. Install [webpack](https://classic.yarnpkg.com/en/package/webpack)

> 
	
	$ yarn add webpack


#### 6. Install [babel-cli](https://classic.yarnpkg.com/en/package/babel-cli), [babel-core](https://classic.yarnpkg.com/en/package/babel-core) & [babel-loader](https://classic.yarnpkg.com/en/package/babel-loader)

>
	
	$ yarn add babel-cli babel-core babel-loader@7.1.1


#### 7. Install [babel-plugin-transform-class-properties](https://classic.yarnpkg.com/en/package/babel-plugin-transform-class-properties), [babel-preset-env](https://classic.yarnpkg.com/en/package/babel-preset-env) & [babel-preset-react](https://classic.yarnpkg.com/en/package/babel-preset-react)

>
	
	$ yarn add babel-plugin-transform-class-properties babel-preset-env babel-preset-react


#### 8. Create a webpack.config.js file in the root directory and add the following:

>
	
	const path = require('path');
	module.exports = {
	entry: './src/app.js',
	output: {
		path: path.join(__dirname,'public'),
		filename: 'bundle.js'
	},
	module: {
		rules: [{
			loader: 'babel-loader',
			test: /.\js$/,
			exclude: /node_modules/
		}]
	},
	devtool: 'cheap-module-eval-source-map'
	}};


#### 9. Create a .babelrc file in the root directory and add the following:

>
	
	{
	"presets": [
		"env",
		"react"
	],
	"plugins": [
		"transform-class-properties"
	]}


#### 10. Add the following scripts to the package.json file (will change if you want to use webpack-dev-server)

>
	
		"scripts": {
	    	"serve": "live-server public/",
	    	"build": "webpack --watch"
	  	}


#### 11. Add the following HTML code to the index.html file inside of /public

> public/index.html
>
		
	<!DOCTYPE html>
	<html>
	<head>
		<meta charset="UTF-8">
		<title>Test React App</title>
	</head>
	<body>
		<div id="app"></div>
		<script src="/bundle.js"></script>
	</body>
	</html>


#### 12. Create a component file inside of /src/components

> src/components/TestReactApp.js
>
		
	import React from 'react';
		
	export default class TestReactApp extends React.Component {
		render() {
    return (
      <h1>It works!</h1>
    );}}


#### 13. Add the following code to the app.js file inside of /src

> src/app.js
>
	
	import React from 'react';
	import ReactDOM from 'react-dom';
	import TestReactApp from './components/TestReactApp';

	ReactDOM.render(<TestReactApp />, document.getElementById('app'));


#### 14. Build and Serve!

> 
	$ yarn run build
	$ yarn run serve

***

#### OR
#### If you want to use _webpack-dev-server_ instead of live-server:


#### 15. Install [webpack-dev-server](https://classic.yarnpkg.com/en/package/webpack-dev-server)
>
	
	$ yarn add webpack-dev-server


#### 16. Update your package.json file to:

>
		
	"scripts": {
	   	"dev-server": "webpack-dev-server"
	}


#### 17. Update the webpack.config.js file to:

>
	
	const path = require('path');
	module.exports = {
	entry: './src/app.js',
	output: {
		path: path.join(__dirname,'public'),
		filename: 'bundle.js'
	},
	module: {
		rules: [{
			loader: 'babel-loader',
			test: /.\js$/,
			exclude: /node_modules/
		}]
	},
	devtool: 'cheap-module-eval-source-map',
	devServer: {
		contentBase: path.join(__dirname,'public')
	}};


#### 18. Build and Serve using webpack only!

>
	
	$ yarn run dev-server


Sources and learning:
[https://www.udemy.com/course/react-2nd-edition/](https://www.udemy.com/course/react-2nd-edition/)