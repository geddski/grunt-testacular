grunt-testacular
================

A wrapper for [grunt](http://gruntjs.com) around
[testacular](http://vojtajina.github.com/testacular/) that lets you
run multiple instances of testacular. 


> For use with the latest testacular checkout `grunt-testacular@canary`.
> This will use version `0.5.5` of testacular.

## Installation

First you need to install this plugin in your project

```bash
$ npm install grunt-testacular
```

then load the tasks in your Gruntfile with

```javascript
grunt.loadNpmTasks('grunt-testacular');
```
And now you can run
```bash
$ grunt testacularServer
```
to start up the server.

## Usage
There are two tasks provided `testacularServer` and `testacularRun`. 

### `testacularServer`
This task is the equivalent of `testacular start <options>
<configFile>`. You can use it to do single runs or to `autoWatch`
files and directories. To use it you need to at least specify a
`configFile`. All other options can be defined in the `configFile` but
you can also override some of these.

**simple example**

```javascript
testacularServer: {
  unit: {
    configFile: 'config/testacular.conf.js'
  }
}
```

**advanced example**

```javascript
testacular: {
  unit: {
    configFile: 'config/testacular.conf.js',
    autoWatch: true,
    browsers: [ 'Chrome', 'PhantomJS' ],
    reporters: [ 'dots' ],
    runnerPort: 9101
  }
}
```
And if you want to keep the server running.
```javascript
testacularServer: {
  unit: {
    options: {
      keepalive: true
    },
    configFile: 'config/testacular.conf.js'
  }
}
```

### `testacularRun`
This task is the equivalent of running `testacular run <options>`.
There is only one option available, that is `portRunner` that defines
the port where the server is listening.

```javascript
testacularRun: {
  unit: {
    runnerPort: 9101
  }
}
```

## Release History
* v0.3.0 - Use testacular@0.5.5 canary.
* v0.2.2 - Add ability to use grunt templates.
* v0.2.1 - Make Grunt 0.4.0a compatible.
* v0.2.0 - Added `keepalive` option.
* v0.1.0 - First release on npm.

## License
Copyright (c) 2012 Friedel Ziegelmayer

Licensed under the MIT license.
