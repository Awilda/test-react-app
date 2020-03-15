# React From Scratch

## Steps

#### 1. Create project directory

> project-app-folder

> > public

>- index.html

> > src
 
>- components

> > app.js


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


#### 5. Install [webpack](https://classic.yarnpkg.com/en/package/webpack) & [webpack-dev-server](https://classic.yarnpkg.com/en/package/webpack-dev-server)

> 
	
	$ yarn add webpack webpack-dev-server


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
	devtool: 'cheap-module-eval-source-map',
	devServer: {
		contentBase: path.join(__dirname,'public')
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


#### 10. 