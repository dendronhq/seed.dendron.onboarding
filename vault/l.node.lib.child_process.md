---
id: 7da24804-4d2a-456c-a43a-374b2ba68e47
title: Child_process
desc: ''
updated: 1600533322089
created: 1600533322089

sources:
  - name: ""
    url: https://nodejs.org/api/child_process.html
    license: ""
---

# Summary

The child_process module provides the ability to spawn child processes in a manner that is similar, but not identical, to popen(3). This capability is primarily provided by the child_process.spawn() function:


# API

### fork

child_process.fork(): spawns a new Node.js process and invokes a specified module with an IPC communication channel established that allows sending messages between parent and child.

- args
    * modulePath <string> The module to run in the child.
    * args <string[]> List of string arguments.
    * options <Object>
        * cwd <string> Current working directory of the child process.
        * detached <boolean> Prepare child to run independently of its parent process. Specific behavior depends on the platform, see options.detached).
        * env <Object> Environment key-value pairs. Default: process.env.
        * execPath <string> Executable used to create the child process.
        * execArgv <string[]> List of string arguments passed to the executable. Default: process.execArgv.
        * serialization <string> Specify the kind of serialization used for sending messages between processes. Possible values are 'json' and 'advanced'. See Advanced serialization for more details. Default: 'json'.
        * silent <boolean> If true, stdin, stdout, and stderr of the child will be piped to the parent, otherwise they will be inherited from the parent, see the 'pipe' and 'inherit' options for child_process.spawn()'s stdio for more details. Default: false.
        * stdio <Array> | <string> See child_process.spawn()'s stdio. When this option is provided, it overrides silent. If the array variant is used, it must contain exactly one item with value 'ipc' or an error will be thrown. For instance [0, 1, 2, 'ipc'].
        * windowsVerbatimArguments <boolean> No quoting or escaping of arguments is done on Windows. Ignored on Unix. Default: false.
        * uid <number> Sets the user identity of the process (see setuid(2)).
        * gid <number> Sets the group identity of the process (see setgid(2)).

- notes
    - Keep in mind that spawned Node.js child processes are independent of the parent with exception of the IPC communication channel that is established between the two. Each process has its own memory, with their own V8 instances. Because of the additional resource allocations required, spawning a large number of child Node.js processes is not recommended.
    - The shell option available in child_process.spawn() is not supported by child_process.fork() and will be ignored if set.


