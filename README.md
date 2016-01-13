# Clojure Interpreter for Zeppelin Notebooks

[![][clj-zep-logo]][clj-zep-logo-large]

[clj-zep-logo]: resources/images/clojurezeppelin-logo-x250.png
[clj-zep-logo-large]: resources/images/clojurezeppelin-logo-x1000.png

*A Clojure Interpreter for Zeppelin Notebooks*


#### Contents

* [Introduction](#introduction-)
* [Dependencies](#dependencies-)
* [Build & Installation](#build-installation-)
* [Configuration](#configuration-)


## Introduction [&#x219F;](#contents)

TBD


## Dependencies [&#x219F;](#contents)

* Zeppelin
* ``lein``


## Build & Installation [&#x219F;](#contents)

This project registers an interpreter named ``clj`` for Zeppelin. To use it,
you first need to build its ``.jar`` file:

```bash
$ lein uberjar
```

This will create the file ``target/clojureinterpreter-0.2.0-standalone.jar``.
Copy this to the ``interpreter`` directory in your ``ZEPPELIN_HOME``, e.g.:

```bash
$ mkdir /opt/zeppelin/0.5.5/interpreter/clj/
$ cp target/clojureinterpreter-0.2.0-standalone.jar /opt/zeppelin/0.5.5/interpreter
```


## Configuration [&#x219F;](#contents)

Once the Clojure interpreter ``.jar`` file is in place, you'll need to
configure Zeppelin to let it know it's available for use. In setting up
Zeppelin, you should have created (or it was created for you) the configuration
file ``$ZEPPELIN_HOME/conf/zeppelin-site.xml``.

1. Open this file
1. Search for the line ``<name>zeppelin.interpreters</name>``
1. After the last interpreter given in the ``<value>`` tag, add a comma and
   then the value ``clojureinterpreter.ClojureInterpreter``; if you want
   Clojure to be your default interpreter, move it to the first value in the
   comma-separatede list of values
1. Save and exit the file
1. Restart Zeppelin, e.g.: ``/opt/zeppelin/0.5.5/bin/zeppelin-daemon.sh restart
1. Load up the notebook in your browser
1. From the "Interpreters" menu at the top, select "Clojure"
1. Click the ``+Create`` button and customize your interpreters settings
1. If you did not configure the Clojure interpreter to be your default, then
   you can use the ``%clj`` directive you declare the Clojure interpreter
