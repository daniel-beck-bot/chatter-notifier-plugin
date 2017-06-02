[![Build Status](https://ci.jenkins.io/buildStatus/icon?job=Plugins/chatter-notifier-plugin/master)](https://ci.jenkins.io/job/Plugins/job/chatter-notifier-plugin/job/master/)

# Chatter plugin for Jenkins

This is a plugin for Jenkins that will post build build results to a Chatter feed. You can configure it to post to a specific User (e.g. a build user), a specific group (e.g. a group that owns the build), or a specific record (perhaps you have a custom object that tracks build configs).

# Install

The plugin is available via the main Jenkins plugin distribution, so goto the manage Jenkins page, manage plugins, and then the available tab and search for Chatter Notifier and pick
the option to install it.

# Configure

With the plug-in installed, and the server restarted, the build configuration page will now have an extra option "Chatter Results", if you select this, then you can 
populate the 4 fields as need (credentials (use the central Jenkins credentials tool to create one), and the recordId to post the results to, leave this blank to post to the users
wall, or enter a record Id to post to that specific record (or group)).

![build feed](http://www.pocketsoap.com/weblog/hc.png)

# Publish Enforce coverage results

This option allows to publish the coverage results generated by [Enforce](https://github.com/fundacionjala/enforce-gradle-plugin), the post should look something like this.

```
Build: SForce-CI-Project-job 2 is SUCCESS
Coverage Result: 76.91% of code coverage, Risk status.
Coverage Status: Danger (0% - 74%): 298 files. Risk (75% - 79%): 84 files. Acceptable (80% - 94%): 267 files. Safe (95% - 100%): 277 files.
Test Result: 0 tests failing out of a total of 3,276 tests.
```

# Build

The plugin is built with Maven, same as Jenkins itself, simply clone to repo and run mvn install, the generated plugin ChatterPlugin.hdi will be in the target directory.

More details on building Jenkins plugins are available on the [Jenkins Wiki](https://wiki.jenkins-ci.org/display/JENKINS/Plugin+tutorial)


