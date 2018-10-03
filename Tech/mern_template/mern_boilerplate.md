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

Good work

---

Now let's start pulling in our dependencies.

### First is ESLINT

You may choose to install this globally or locally.

`npm i -g eslint` or `sudo npm i -g eslint`. To install locally, simply remove the `-g` flag.

In your terminal run this

```
$ eslint --init
```

choose `recommended`