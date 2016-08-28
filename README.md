![node-playbook banner](http://i.imgur.com/LUyKH8K.png)

# node-playbook

This is a opinionated guide to developing with Node.js. It helps you get started in a world of infinite options, rather than spending days researching basic choices.

Some of the advice is not specific to Node.js.

It is not the only way to develop with Node.js. It does not teach you how to program in JavaScript.

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
