When a Node.js application crashes, it is often desirable to be able to
investigate why it crashed. The problem is that, since the process is not
running anymore, it is impossible to attach a debugger to it.

Fortunately, Node.js can generate a core file every time the application
throws an unhandled exception. With this core file, it is possible to examine
the state of the application when it crashed and determine the root cause.

In order to allow Node.js to generate a core file every time an unhandled
exception is raised, you will need to do two things:

1) Setup your operating system so that it can generate core files for
applications that abort. You will need to use the `coreadm` command to enable
core files generation and to set the path to where they should be written. You
will also need to use the `ulimit` command to remove the limit on the core
files size.

2) Pass the `--abort-on-uncaught-exception` command line switch to the `node`
program when starting your application.

To complete this exercise, write a shell script that generates a core file
from a Node.js application in the directory `{coresDirectory}`, with a file name that
follows this pattern:
```
core.pid
```
where `pid` is the id of the node process that aborted.

The Node.js application should only output its process ID to the standard
output.

To verify your solution, run the following command line:
```
$ node-debug-school verify shell-script.sh
```
where `shell-script.sh` is the path to your shell script.


