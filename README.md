core.matrix
===========

[![Clojars Project](http://clojars.org/net.mikera/core.matrix/latest-version.svg)](http://clojars.org/net.mikera/core.matrix)

[![Build Status](https://travis-ci.org/mikera/core.matrix.png?branch=master)](https://travis-ci.org/mikera/core.matrix) [![Dependency Status](https://www.versioneye.com/user/projects/54deecf4271c9379ed000042/badge.svg?style=flat)](https://www.versioneye.com/user/projects/54deecf4271c9379ed000042)

The core.matrix library provides array programming as a language extension for
Clojure/Clojurescript, with a focus on numerical computing.

core.matrix will become an official part of Clojure Contrib now that the 
API is mature and proven, at which point this repo will move to org.clojure/core.matrix

The central objective of `core.matrix` is to make matrix and array programming
idiomatic, productive, elegant and fast in the Clojure environment.

```clojure
(+ [[1 2]
    [3 4]]
   (* (identity-matrix 2) 3.0))

=> [[4.0 2.0]
    [3.0 7.0]]

(shape [[2 3 4] [5 6 7]]) ; => [2 3]

(mmul
  (array [[2 2] [3 3]])
  (array [[4 4] [5 5]])) ; => [[18 18] [27 27]]

;; Note: nested Clojure vectors can be used as matrices
```

Key goals of *core.matrix*:

 - Provide a clear, standard API / abstraction for **matrix and array programming** in Clojure
 - Enable **pluggable** support for different underlying matrix library implementations
 - Provide general purpose **n-dimensional array** implementations
 - Provide a **foundation** for other projects in the ecosystem (e.g. Incanter)
 - Enable **high performance** numerical computing
 - Allow **idiomatic** Clojure coding for numerical code

### Documentation

For general `core.matrix` documentation and examples see the Wiki:

 - https://github.com/mikera/core.matrix/wiki

API documentation is available here

 - https://mikera.github.io/core.matrix/doc/index.html

For a general introduction, the slide and video from the 2013 Clojure Conj talk are available here:

 - http://www.slideshare.net/mikeranderson/2013-1114-enter-thematrix
 - http://www.youtube.com/watch?v=_h9TLJtjSJo

### Clojurescript

To develop for clojurescript you will need to use the cljs-dev profile
like this:

    lein with-profile +cljs-dev repl

or using figwheel:

    lein with-profile +cljs-dev figwheel

To build the Clojurescript unit tests you can run:

    lein with-profile +cljs cljsbuild once

and then load resources/public/test.html in a browser to run the tests.

To test under self-hosted ClojureScript:

     lein with-profile +cljs doo planck test once

### Status

`core.matrix` is fully functional and usable in production applications. As well as supporting
the standard Clojure data structures, multiple back end implementations exist that provide optimised
matrix implementations. The most mature implementations are currently:

 - [**vectorz-clj**](https://github.com/mikera/vectorz-clj) : a fast pure-JVM matrix library for Clojure, supporting full ND arrays
 - [**Clatrix**](https://github.com/tel/clatrix) : native code matrix library using BLAS
 - **NDArray** : a general purpose pure Clojure N-dimensional array implementation, included as part of `core.matrix` itself
 - [**nd4clj**](https://github.com/ds923y/nd4clj) : This is a wrapper around the [Nd4j](http://nd4j.org) api a native code and GPU accelerated matrix library

For Clojurescript:

 - [**aljabr**](https://github.com/thinktopic/aljabr) : a cljc matrix library supporting Clojurescript

The API is relatively mature but still *subject to some changes* at present (at least up until release 1.0.0),
so users should be prepared to deal with potential breaking changes when updating to future releases.


### Contributing

All contributions / ideas welcome!

There are a number of proposed enhancements listed as GitHub issues: these are a good place to start if you wish to contribute
to core.matrix:

 - https://github.com/mikera/core.matrix/issues?state=open

If you wish to contribute code, please ensure you have a **Clojure Contributors Agreement** signed and on file. For more information see:

 - http://clojure.org/contributing

Discussions related to core.matrix generally take place on the "Numerical Clojure" group:

 - https://groups.google.com/forum/?fromgroups#!forum/numerical-clojure

If you are interested in writing a `core.matrix` implementation, see:

 - https://github.com/mikera/core.matrix/wiki/Implementation-Guide

You can also find a protocol implementation summary here:

 - http://mikera.github.io/core.matrix/summary.html

### Thanks

YourKit is kindly supporting this open source project with its full-featured Java Profiler.
YourKit, LLC is the creator of innovative and intelligent tools for profiling
Java and .NET applications. Take a look at YourKit's leading software products:
<a href="http://www.yourkit.com/java/profiler/index.jsp">YourKit Java Profiler</a> and
<a href="http://www.yourkit.com/.net/profiler/index.jsp">YourKit .NET Profiler</a>.
