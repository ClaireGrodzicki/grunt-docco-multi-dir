Grunt-docco-multi-dir is an improvement on grunt-docco-multi and employs some of the desired end results of grunt-docco-dir.  

Grunt-docco-multi-dir uses a modified version of docco, called docco-multidir.  These changes allow 



## Improvements
* A new docco option called `projectName` is passed into the template for rendering.  This is coupled with other changes in docco-multidir, which put the full path to the file on the template.
* Updated the code to use docco-multidir as a dependency, and not docco.
* Everything else is the same as "grunt-docco-multi" : "~0.0.2"


## Installation

Install npm package, next to your project's Gruntfile:

    npm install --save-dev grunt-docco-multi-dir

Add this line to your project's Gruntfile:

    grunt.loadNpmTasks('grunt-docco-multi-dir');


## Version

    "grunt-docco-multi" : "~1.0.0"

## Configuration

`docco` is a multitask, so you can use it similary to `lint`, `watch` etc...


  grunt.initConfig

    ...

    docco:

      # ## use current sane defaults
      options:
        layout : "parallel"
        output : "docs/"
        projectName: "{insert your project name here}"

      # ## parse multiple files
      all:
        files:
          src: ['test/fixtures/*.coffee']

      # ## parse a single file
      single:
        files:
          src: ['test/fixtures/valid.litcoffee']

      # ## parse this file with linear output
      gruntfile:
        options:
          layout: "linear"
        files:
          src: 'Gruntfile.coffee'

      # ## nothing to parse
      empty: '404.coffee'

    ...

### Options

Standard `docco` options are supported

    config:
        layout:     'parallel'
        output:     'docs/'
        template:   null
        css:        null
        extension:  null
        projectName: '{insert your project name here}'
