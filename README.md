![node-playbook banner](http://i.imgur.com/LUyKH8K.png)

# node-playbook

This is a opinionated guide to developing with Node.js. It helps you get started in a world of infinite options, rather than spending days researching basic choices.

Some of the advice is not specific to Node.js.

This is not the only way to develop with Node.js. This playbook does not teach you how to program in JavaScript. It does not replace the need to read documentation.

## Contents

1. [The Golden Rule: avoid coding wherever possible](#the-golden-rule-avoid-coding-wherever-possible)
1. [Node.js version](#nodejs-version)
1. [Development environment](#development-environment)
1. [Coding style](#coding-style)
1. [Version numbering](#version-numbering)
1. [Native modules & Windows](#native-modules--windows)

## The Golden Rule: avoid coding wherever possible
You should aim to be **optimally lazy**. There are only two principles:

1. The fastest way to finish a task is to do nothing
  * Ask yourself if you can live without it
  * Less code means less bugs
  * See also: [YAGNI](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)
1. The second fastest way to finish a task is to get someone else to do it
  * For example, this playbook is an example of using someone else's work to get ahead
  * Use [Node.js core API](https://nodejs.org/api/) if you can get away with it
  * Use pre-built pieces of code, such as [npm modules](https://www.npmjs.com/)
    * Make sure your dependencies are of high quality

## Node.js version
### Problem / Context
Many versions are listed on the Node.js website. Choosing a Node.js version wastes time.
### Recommended solution
Choose [Node.js v6](https://nodejs.org/dist/latest-v6.x/). It will enter long term support (LTS) on October 1, 2016, after which it will stay in LTS for 18 months. This gives you peace of mind against brand new features popping up in Node.js while you build your app.

## Development environment
### Problem / Context
Choosing a development environment (e.g. editors, git GUIs, terminals, FTP clients) wastes time. No tool is 10 times better than another. You need a set of tools that get you started and let you grow according to you needs.
### Recommended solution
Here is a set of tools that will get you going:
* Editor: [Atom](https://atom.io/)
  * Atom packages/plug-ins:
    * atom-beautify
    * atom-html-preview
    * fold-lines
    * terminal-plus
    * markdown-preview (hit Ctrl+Shift+M)
* Version control: [git](https://git-scm.com/)
* Repo hosting: [GitHub](https://github.com/)
  * for private repos: either pay GitHub or use [BitBucket](https://bitbucket.org/) instead
* Git GUI: [SourceTree](https://www.sourcetreeapp.com/) (why: clone repos from GitHub *and* BitBucket)
* API testing: [Postman](https://www.getpostman.com/apps)
* Socket testing: [Socket.io tester](https://chrome.google.com/webstore/detail/socketio-tester/cgmimdpepcncnjgclhnhghdooepibakm?hl=en)

Download and install from each link above.

## Coding style
### Problem / Context
Fretting over coding style wastes time, and a sloppy coding style reflects poorly on you. You need a coding style that looks decent and is easy to follow.
### Recommended solution
Follow [Airbnb's Javascript Style Guide](https://github.com/airbnb/javascript)

## Version numbering
### Problem / Context
Deciding on a version number scheme wastes time. Using a non-standard scheme confuses anyone using your package.
### Recommended solution
Use [Semantic Versioning](http://semver.org/) (a.k.a. semver). Here are the most important bits to get started:

> Given a version number MAJOR.MINOR.PATCH, increment the:
>
> 1. MAJOR version when you make incompatible API changes,
> 2. MINOR version when you add functionality in a backwards-compatible manner, and
> 3. PATCH version when you make backwards-compatible bug fixes.
>
> How should I deal with revisions in the 0.y.z initial development phase?
>
> The simplest thing to do is start your initial development release at 0.1.0 and then increment the minor version for each subsequent release.
>
> How do I know when to release 1.0.0?
>
> If your software is being used in production, it should probably already be 1.0.0. If you have a stable API on which users have come to depend, you should be 1.0.0. If you’re worrying a lot about backwards compatibility, you should probably already be 1.0.0.

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

This is the simplest solution as it eliminates the problem rather than trying to accommodate it. The speed advantage from the native module will not be missed until later in your development cycle.
### Other solutions
See the Windows installation instructions at the [node-gyp README](https://github.com/nodejs/node-gyp#Installation). I never got this to work despite many tries.

## License

MIT License

Copyright (c) 2016 Faraz Syed

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
