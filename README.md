![node-playbook banner](http://i.imgur.com/LUyKH8K.png)

# node-playbook

This is a opinionated guide to developing with Node.js. It helps you get started in a world of infinite options, rather than spending days researching basic choices.

It is not the only way to develop with Node.js. It does not teach you how to program in JavaScript.

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
