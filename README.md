# Node.js Debug School

This is a workshop to learn about how to do debugging of Node.js applications
in production, including postmortem debugging.

## Prerequisites

### SmartOS

__You will need an access to a SmartOS instance to run this workshop.__ To get
an access to a SmartOS instance, the best way is to [sign up for an account on
Joyent's Public Cloud](https://my.joyent.com/landing/signup/701800000015N22)
and use the free services tier.

The reason for such a requirement is that SmartOS _currently_ provides the
best experience for postmortem debugging of Node.js applications. Later, you
will be able to run this workshop on other platforms. For instance, TJ
Fontaine has been working on [v8 support for
lldb](https://github.com/tjfontaine/lldb-v8), which should help porting this
workshop to any platform where lldb is available.

## How to start the workshop?

Simply install node-debug-school globally (you will need root access to do that):
```
$ npm install -g git+https://git@github.com/joyent/node-debug-school.git
```
and start `node-debug-school`:
```
$ node-debug-school
```

You will be presented with a series of exercises, each containing instructions
on how to complete them.

### Command line options

#### --dev

`--dev` is for _development mode_.

Use `--dev` if you'd like to run the workshop without checking if you're using
a supported platform. This is useful when developping or testing the workshop
on an unsupported platform.

### Supported platforms

Currently, the only supported platform is SmartOS, because mdb and mdb's v8
module are needed to complete most exercises. However, if you'd like to run
the workshop on an unsupported platform, you can still use the `--dev` command
line switch. It will bypass any platform check. Keep in mind however that some
parts of the workshop might not work correctly.
