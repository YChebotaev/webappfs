webappfs
========

Generic directory structure for web application

root file system structure
```plain
/web
  /apps
  /conf.d
  /logs
  /pids
```

file system structure
---------------------

```plain
/web
  /apps
    /<appname>
      /<environment>
  /conf.d
    /<programname>
      /*.*
      /<appname>
        /*.*
        /<environment>
          /*.*
    /<appname>
      /*.*
      /<environment>
        /*.*
  /logs
    /<programname>
      /*.*
      /<appname>
        /*.*
    /<appname>
      /<environment>
        /*.*
  /pids
    /<appname>
      /<environment>
        /*.*
      /<programname>
        /*.*
```

`appname` means your application name e.g. `example`

`programname` means 3rd party or system program that requires for running application

`environment` is tier name that denotes a running environment of web app e.g. `stage`, `test`, `prod`

`*.*` means any set of files inside parent directory

example structure (nginx + node.js + forever)
=============================================

This structure intended for convinient way of deploying web applications for `node.js` projects.

```plain
/web
  /apps
    /example
      /production
        /package.json
        /app.js
        /public
          /index.html
      /staging
        /package.json
        /app.js
        /public
          /index.html
  /conf.d
    /nginx
      /example
        /production
          /nginx.conf
        /staging
          /nginx.conf
    /forever
      /example
        /staging
          /config.json
        /production
          /config.json
  /logs
    /example
      /production
        /forever.log
        /stdout.log
        /stderr.log
      /staging
        /forever.log
        /stdout.log
        /stderr.log
  /pids
    /example
      /production
        /pid
      /staging
        /pid
```
