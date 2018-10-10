# Create a MERN app boilerplate

Quite too often we rely on CLI's to help us bootstrap our projects, while this is a great step towards reducing your development time, and cutting down on the amount of stress it takes to understand the technicalities involved, that is if you are new to the technology...
You would discover as you progress and gain mastery of the art and tech that there begins to well up a need to understand what is happening behind the scene. I've been in these places all through my coding journey, and if you are then this post is for you.

## What you will learn

In this post, am going to show you how to build a MERN (Mongodb, Express, React, Node) boilerplate from scratch. If you have ever used `express generator` or `create-react-app` you will relate better with this.

I will be trying my best to show you how and what is happening behind the scene so you extend and do what ever you like after knowing the basis.

## The Future

Prior to [create react app v2](https://github.com/facebook/create-react-app/releases), there were some reasons developers `ejected` from the default CRA bootstrapping. I had mine as well, one of them being the inability to use [sass](https://sass-lang.com/). This limitation drove me to find other ways of setting up CRA.

Alright let's get to work 👍

Open your terminal and run this command

```sh
$ mkdir mern_boilerplate && cd mern_boilerplate
```

Next you create a couple directories.

```
$ mkdir client backend
```

From the root of your project run `npm init -y`. The `-y` flag will automatically answer yes to all the prompts.

Good work. I like to have a single `npm` file where I manage all dependencies. I can't say what's right or wrong about the approach, you could choose to manage your dependencies within thier separate directories.

---

Now let's start pulling in our dependencies.

Your directory tree should look like this

```txt
| src
  - backend
  - client
  - package.json
```

### First is ESLINT

You may choose to install this globally or locally.

`npm i -g eslint` or `sudo npm i -g eslint`. To install locally, simply remove the `-g` flag.

In your terminal run this

```
$ eslint --init
```

choose

- Use a popular style guide
- Airbnb
- `Do you use React?` type `yes` or `y`
- JSON

It automatically checks for peer dependencies and downloads them.

Now your `package.json` should look like this

![package.json](./assets/packagejson.png)

while your `.eslintrc.json` should have the following

```json
{
  "extends": "airbnb"
}
```

### Babel & Webpack

Now let's go ahead and install [babel](https://babeljs.io/) and [webpack](https://webpack.js.org/).

- `Babel`: is a javascript compiler. It is a toolchain that is mainly used to convert `ECMAScript 2015+` code into a backwards compatible version of JavaScript in current and older browsers or environments. Visit the [Docs](https://babeljs.io/docs/en/) for more information.

- `Webpack`: is a static module bundler for modern JavaScript applications. When webpack processes your application, it internally builds a dependency graph which maps every module your project needs and generates one or more bundles. Visit the [Docs](https://webpack.js.org/concepts/) for more information.

Now run this in your terminal

```sh
$ npm i babel-cli babel-core babel-loader babel-plugin-transform-class-properties babel-preset-env babel-preset-react
```

That's probably a lot of dependencies you may think. This is what babel needs to compile our code properly.

Install `webpack` via the terminal

```
$ npm i webpack webpack-dev-server
```

Now create a file `.babelrc` and register this inside.

```.bablerc
{
  "presets": ["env", "react"],
  "plugins" ["transform-class-properties"]
}
```

The setup above will allow us to use ES6 and `javascript's` spread syntax in our code.

## Configuring Webpack

Create a file `webpack.config.js` in the root of your project and register the following code inside of it.

```js
const path = require('path')
const HtmlWebpackPlugin = require('html-webpack-plugin')

module.exports = {
  entry: "./client/src/index.js",
  output: {
    path: path.resolve(__dirname, "./dist"),
    filename: "index-bundle.js"
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        loader: "babel-loader"
      },
      {
        test: /\.s?css$/,
        use: ["style-loader", "css-loader", "sass-loader"]
      }
    ]
  },
  plugins: [
    new HtmlWebpackPlugin({
      template: "./client/public/index.html"
    })
  ],
  devtool: "cheap-module-eval-source-map",
  devServer: {
    contentBase: path.resolve(__dirname, "./dist")
  }
}
```

Very good. At the moment our project has some missing dependecies listed in our `webpack.config.js` file. We will fix that by installing those real quick. So head to the terminal and run this:

```sh
$ npm i style-loader css-loader sass-loader
$ npm i --save-dev html-webpack-plugin
```

Great work 🙂.