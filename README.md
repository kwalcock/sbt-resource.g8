# sbt-resource.g8

This is a [Giter8](http://foundweekends.org/giter8) template for creating an `sbt` project that manages publication of resources for the [CLU Lab](http://github.com/clulab).  Being for resources, there is no building involved beyond the zipping up of the files into a jar so that it can be readily accessed by Scala/Java.  It is specifically for the CLU Lab because it includes URLs to the lab's [Artifactory](http://artifactory.cs.arizona.edu:8081/artifactory/webapp/#/home) and [Sonatype](https://oss.sonatype.org/index.html#nexus-search;quick~clulab) servers, which wouldn't work for other groups.

To use this project as a template for an `sbt` project, do not clone it, but instead run
```
$ sbt new http://github.com/clulab/sbt-resource.g8.git
```
and when prompted, give values for `name` and specify whether it is `artifactory` or `maven` that should be used to publish the resource.  This should result in an `sbt` project called `<name>` in the current directory of your hard drive.  Copy your resource to an appropriate subdirectory, something under `src/main/resources/org/clulab/<name>`.  Files from there will be added to the `jar` file that gets published.  The project's `README.md` file should explain the steps of that process.

If you want to modify how the template gets generated, then do clone the project from `github` and change what you'd like.  Test it by running `g8` from `sbt` and finding the results in the `./target/g8` directory.
```
$ git clone http://githubcom/clulab/sbt-resource.g8
$ cd sbt-resource.g8
$ sbt g8
$ cd target/g8
```
The template language used by `g8` is taken from [StringTemplate](https://github.com/antlr/stringtemplate4/) and its [documentation](https://github.com/antlr/stringtemplate4/blob/master/doc/index.md) is very helpful.
