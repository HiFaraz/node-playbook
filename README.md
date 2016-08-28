![node-playbook banner](http://i.imgur.com/C1yh7Wj.png)

# Node.js Playbook

This is a opinionated "get started" guide to developing with Node.js.

### Problem / Context
You waste time by:

* discovering/researching basic aspects of Node.js development, and
* choosing from amongst several tool options that do the same job

### Recommended solution
Follow this playbook. It recommends basic choices that let you focus on writing code instead of setting things up.

### Who this is for

* Beginners who just want to get a project started without too much hassle
* Veterans who want a quick reference guide to unfamiliar parts of the Node.js ecosystem

### What this is not

* This does not teach you JavaScript
* This is not the only way to develop with Node.js. Use this playbook to get started, then use other choices when applicable
* This does not replace the need to read documentation
* Not all advice is specific to Node.js

## Contents

1. [The Golden Rule: avoid coding wherever possible](#the-golden-rule-avoid-coding-wherever-possible)
1. [General problems](#general-problems)
  1. [Node.js version](#nodejs-version)
  1. [Development environment](#development-environment)
  1. [Workflow](#workflow)
  1. [File and folder structure](#file-and-folder-structure)
  1. [Coding style](#coding-style)
  1. [Native modules and Windows](#native-modules-and-windows)
1. [Developing for the web](#developing-for-the-web)
  1. [Technology stack](#technology-stack)
1. [Developing a package](#developing-a-package)
  1. [Version numbering](#version-numbering)
1. [Developing mobile applications](#developing-mobile-applications)
1. [Developing desktop applications](#developing-desktop-applications)
  1. [Cross platform framework](#cross-platform-framework)
1. [Upcoming sections](#upcoming-sections)
1. [Contributing](#contributing)
1. [License](#license)

# The Golden Rule: avoid coding wherever possible
Be **optimally lazy**. There are only two principles:

1. The fastest way to finish a task is to do nothing
  * Ask yourself if you can live without it
  * Less code means less bugs
  * See also:
    * [You aren't gonna need it](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it) (YAGNI)
    * [Customer development](http://www.startuplessonslearned.com/2008/11/what-is-customer-development.html)
    * [Minimum viable product](http://www.startuplessonslearned.com/2009/08/minimum-viable-product-guide.html) (MVP)
1. The second fastest way to finish a task is to get someone else to do it
  * For example, this playbook is an example of using someone else's work to get ahead
  * Use [Node.js core API](https://nodejs.org/api/) if you can get away with it
  * Use pre-built pieces of code, such as [npm modules](https://www.npmjs.com/)
    * Make sure your dependencies are of high quality

# General problems
This section covers general problems regardless of your development goals.

## Node.js version
### Problem / Context
Many versions are listed on the Node.js website. Choosing a Node.js version wastes time.
### Recommended solution
Choose [Node.js v6](https://nodejs.org/dist/latest-v6.x/). It will enter long term support (LTS) on October 1, 2016, after which it will stay in LTS for 18 months. This gives you peace of mind against major new features popping up in Node.js while you build your app.

## Development environment
### Problem / Context
Choosing a development environment (e.g. editors, git GUIs, terminals, FTP clients) wastes time. No tool is 10 times better than another. You need a set of tools that get you started and let you grow according to you needs.
### Recommended solution
Download and install these tools:
* Editor: [Atom](https://atom.io/)
  * Atom packages/plug-ins:
    * atom-beautify (go into `Settings > Packages` and enable `Beautify On Save` for CSS, HTML, JavaScript, JSON, and Markdown)
    * atom-html-preview (press `Ctrl+P` in the editor to open the preview)
    * fold-lines
    * terminal-plus
    * markdown-preview (press `Ctrl+Shift+M` in the editor to open the preview)
* Version control: [git](https://git-scm.com/)
* Repository (repo) hosting: [GitHub](https://github.com/)
  * for private repos: either pay GitHub or use [BitBucket](https://bitbucket.org/) instead
* Git GUI: [SourceTree](https://www.sourcetreeapp.com/) (why: you can upload/push much faster and clone repos from GitHub *and* BitBucket)
* API testing: [Postman](https://www.getpostman.com/apps)
* Socket testing: [Socket.io tester](https://chrome.google.com/webstore/detail/socketio-tester/cgmimdpepcncnjgclhnhghdooepibakm?hl=en)

## Workflow
### Problem / Context
Thinking about how to set up a new project wastes time.
### Recommended solution
1. Create a new repo on either GitHub or BitBucket
  * Choose Node under the gitignore settings when creating a repo
  * Choose to create a README.md
1. Clone it to your computer with either a terminal command or with SourceTree
1. Set up your [file and folder structure](#file-and-folder-structure)
1. Open a terminal window in your repo folder (or use the Terminal button when you open the repo in SourceTree)
1. Run `npm init` in your terminal to create a `package.json` file
  * Set your initial version to 0.1.0 (see also [version numbering](#version-numbering))
  * If this is an open source project then choose an MIT license by typing `MIT` when prompted for a license name
1. Run `atom ./` in your terminal to launch Atom in your project folder

## File and folder structure
### Problem / Context
Thinking about how to set up your project file and folder structure wastes time.
### Recommended solution
1. Create three subfolders:
  1. `source`: place all your source code here
  1. `test`: place all testing code here
  1. `build` (optional): use this as a destination folder if/when you implement a build system (something that converts your source code to another form)
1. Create a file in the `source` sub-folder called `index.js`

## Coding style
### Problem / Context
Fretting over coding style wastes time, and a sloppy coding style reflects poorly on you. You need a coding style that looks decent and is easy to follow.
### Recommended solution
Follow [Airbnb's Javascript Style Guide](https://github.com/airbnb/javascript)

## Native modules and Windows
### Problem / Context
Some npm packages do not install on Windows because they contain non-JavaScript code. You will see errors related to `node-gyp` when you try to install them.
### Recommended solution
Find another npm package that does the job in pure JavaScript. For example, [bcryptjs](https://www.npmjs.com/package/bcryptjs) is a drop-in replacement for the popular [bcrypt](https://www.npmjs.com/package/bcrypt) module.

How to find alternatives:
* if the repo is hosted on GitHub or a similar platform, search the Issues for anyone mentioning Windows or node-gyp. It is likely someone in the thread has linked to a pure JavaScript replacement
* search online

Make sure that your chosen alternative is a suitable replacement. Look for:
* recently active contributors
* good documentation
* number of downloads

This is the simplest solution as it eliminates the problem rather than trying to accommodate it. The speed advantage from the native module will not be missed until later in your development cycle.
### Alternative solution
Do this **if and only if** you cannot find a suitable alternative npm package.

Follow the Windows installation instructions at the [node-gyp README](https://github.com/nodejs/node-gyp#Installation).

I never got this to work despite many tries.

# Developing for the web
This section covers problems commonly encountered with developing, deploying, and distributing web applications.

## Technology stack
### Problem / Context
Choosing a technology stack (e.g. server framework, database, front-end framework, hosting platform) wastes time. Every stack is different and affects your project, however this is mostly a matter of style. Every stack will do the job.
### Recommended solution
* Back-end:
  * Hosting: [Heroku](https://www.heroku.com/)
  * Server framework: [express](https://www.npmjs.com/package/express)
  * Database: PostgresSQL (host it on Heroku)
  * Object-relational mapping: [Sequelize](https://www.npmjs.com/package/sequelize)
* Front-end
  * Domain: [Namecheap](https://www.namecheap.com/domains/registration.aspx?aff=103766) (affiliate link) [[non-affiliate link](https://www.namecheap.com/domains/registration.aspx)]
  * Hosting: [Namecheap](https://www.namecheap.com/hosting/shared.aspx?aff=103766) (affiliate link) [[non-affiliate link](https://www.namecheap.com/hosting/shared.aspx)] (looking for free CDN suggestions that support custom domains)
  * JavaScript: no recommendation yet
  * Styling: [Bootstrap](http://getbootstrap.com/)

# Developing a package
This section covers problems commonly encountered with developing and publishing reusable packages.

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

# Developing mobile applications
This section covers problems commonly encountered with:
* developing and distributing native mobile applications in JavaScript
* serving mobile users for web applications

I am seeking contributors for this section.

# Developing desktop applications
This section covers problems commonly encountered with developing and distributing desktop applications.

I am seeking contributors for this section.

## Cross platform framework
### Problem / Context
Deciding which cross platform framework to use is a waste of time.
### Recommended solution
Use [Electron](http://electron.atom.io/). It is now considered stable as version 1 was released on May 11, 2016. It is backed by the makers of GitHub and Atom, and has a strong community. Electron apps build and run on Mac, Windows, andd Linux.

## Upcoming sections

* General problems
  * Clustering (solution: throng)
  * Password hashing (solution: bcrypt)
  * Saving exact and secure dependency versions (solution: --save-exact, --secure, and .npmrc)
  * Good documentation / READMEs
  * Debug logging (solution: debug)
  * Event emitter (solution: eventemitter3)
  * testing
  * user analytics and app monitoring
  * other analytics: keen.io, google analytics and kissmetrics, and key metrics
  * npm publish scripts that update version number for you
  * promises and callbacks
* Developing for the web
  * Working with sockets (solution: socket.io)
  * Creating a REST API server (solution: Swagger)
  * Deploying serverless (solution: serverless and AWS Lambda
  * Application architecture (solution: single page apps with a back-end API server)
  * Handling server overload (solution: toobusy)
  * Rate limiting and prevent brute force logins
  * Authentication (solution: jsonwebtoken)
  * don't run your server on port 80 or 453
  * security
  * ssl
* Developing mobile applications
  * immediate user feedback for server requests

## Contributing
Contributions are welcome through pull requests and Github Issues.

Specific help I'm looking for:
* someone to write a section called **Developing for mobile platforms**

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
