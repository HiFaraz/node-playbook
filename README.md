# node-playbook
Notes on developing with Node.js

This document is a guide to solving common problems when developing in Node.js. It does not teach you how to program in JavaScript.

## Native modules & Windows
### Problem / Context
Some npm modules do not work on Windows because they contain non-JavaScript code. You will see errors related to `node-gyp` when you try to install them.
### Recommended solution
Find another npm module that does the job in pure JavaScript. For example, [bcryptjs](https://www.npmjs.com/package/bcryptjs) is a drop-in replacement for the popular [bcrypt](https://www.npmjs.com/package/bcrypt) module.

How to find alternatives:
* if the repo is hosted on GitHub or a similar platform, search the Issues for anyone mentioning Windows or node-gyp. It is likely someone in the thread has linked to a pure JavaScript replacement
* search online

Make sure that your chosen alternative is a suitable replacement. Look for:
* recently active contributors
* good documentation
* number of downloads

This is the simplest solution as it eliminates the problem rather than trying to accommodate it.
### Other solutions
See the Windows installation instructions at the [node-gyp README](https://github.com/nodejs/node-gyp#Installation). I never got this to work despite many tries.
