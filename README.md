[![node-playbook banner](http://i.imgur.com/C1yh7Wj.png)](http://nodeplaybook.com)

# Node.js Playbook

Node.js Playbook is an opinionated "get started" guide to developing with Node.js.

The playbook helps you in two ways:
* **solving problems:** if you have a specific need, it gives you a solution that works for most people
* **discovering new ideas**: if you just browse, you will learn new things that can help your project

[Click here to jump to the table of contents](#contents)

### Who this is for

* **Beginners** who just want to get a project started without too much hassle
* **Experience programmers** who want a "get started" guide to unfamiliar parts of the Node.js ecosystem

### How to use this playbook

The playbook is a learning tool, and you must understand its limitations.

* Read documentation and tutorials to implement any solution. The playbook does not replace them
* This does not teach you how to program
* This does not teach you JavaScript
* This is **not the only way** to develop with Node.js. Use this playbook to get started, and keep learning about other ways to solve do things in Node.js
* This is **not the best way** to develop with Node.js. It is *a way* that is good enough to get started without a lot of learning overhead. Once your project grows in complexity you are expected to find solutions that are a better fit for your needs
* Not all advice is specific to Node.js

**Do not use this playbook as your only source of learning.** The playbook only gives you the most broadly applicable solution. As your needs grow you should explore other solutions. This is not the be all and end all of Node.js development. It should only be a part of your learning experience and exploration, not the whole.

### How solutions were chosen

Each solution was chosen after balancing:

* is it stable? (look for a version 1)
* is it actively maintained?
* does it have good documentation?
* is it popular? (so that you can find lots of tutorials and a support community)
* is it free and open source? (as much as possible, except for hosting and domains)
* is it easy to learn?
* is it practical to use daily?
* does it work well with the rest of the playbook?

## Contents

1. [The Golden Rule: avoid coding wherever possible](#the-golden-rule-avoid-coding-wherever-possible)
1. [General](#general)
  1. [Installing Node.js](#installing-nodejs)
  1. [Development environment](#development-environment)
  1. [Workflow](#workflow)
  1. [File and folder structure](#file-and-folder-structure)
  1. [Coding style](#coding-style)
  1. [Native modules and Windows](#native-modules-and-windows)
1. [Web](#web)
  1. [Technology stack](#technology-stack)
1. [Mobile](#mobile)
1. [Desktop](#desktop)
  1. [Multi-OS framework](#multi-os-framework)
1. [Packages](#packages)
  1. [Version numbering](#version-numbering)
1. [Upcoming sections](#upcoming-sections)
1. [Contributing](#contributing)
  1. [Acknowledgements](#acknowledgements)
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
  * Use pre-built pieces of code, such as [npm packages](https://www.npmjs.com/)
    * Make sure you use high quality dependencies

[(back to top)](#contents)

# General
This section covers general problems regardless of your development goals.

## Installing Node.js
### Goal
Install Node.js.

This sounds simple enough, but unfortunately the Node.js website makes you choose a version of Node.js to download.
### Solution
Choose [Node.js v6](https://nodejs.org/dist/latest-v6.x/). It will enter long term support (LTS) on October 1, 2016, after which it will stay in LTS for 18 months. This gives you peace of mind against major new features popping up in Node.js while you build your app. This advice expires on April 1, 2019.

[(back to top)](#contents)

## Development environment
### Goal
Set up a development environment (e.g. editors, git GUIs, terminals, FTP clients) that gets you started and lets you grow according to you needs.
### Solution
Download and install these tools:
* Editor: [Atom](https://atom.io/)
  * Atom packages/plug-ins:
    * [Package Installation script here](https://gist.github.com/talkahe/25d1f34d2aec3cf662b29309ec08635d)
    * `atom-beautify` ( `Ctrl/Cmd+comma` ➔ `Packages` ➔ Search for `atom-beautify` ➔ `Settings` ➔ toggle the `Beautify On Save` option for every language you want)
    * `atom-html-preview` (press `Ctrl/Cmd+P` in the editor to open the preview)
    * `fold-lines`
    * `platformio-ide-terminal` (terminal at bottom of editor)
    * `markdown-preview` (press `Ctrl/Cmd+Shift+M` in the editor to open the preview)
    * `linter` (A linter is a small program that checks code for stylistic or programming errors. [Available linters](http://atomlinter.github.io/) )
    * `linter-jshint` (JavaScript linter)
    * `highlight-selected` (Double click on a word to highlight it throughout the open file.)
    * `minimap` (broad overview of code)
    * `minimap-cursorline`
    * `atom-typescript` (`.ts` support for atom)
    * `autoclose-html`
    * `double-tag` (edit HTML open and close tags simultaneously)
    * `color-picker` (highlight a color, right click, choose color-picker. Can view & edit colors visually)
    * `package-sync` (save atom packages across computers with a config file)
* Version control: [git](https://git-scm.com/)
* Repository (repo) hosting: [GitHub](https://github.com/)
  * [free private repos for students](https://education.github.com/)
* Git GUI: [SourceTree](https://www.sourcetreeapp.com/)
* API testing: [Postman](https://www.getpostman.com/apps)
* Socket testing: [Socket.io tester](https://chrome.google.com/webstore/detail/socketio-tester/cgmimdpepcncnjgclhnhghdooepibakm?hl=en)

[(back to top)](#contents)

## Workflow
### Goal
Set up a brand new project.
### Solution
1. Create a new repo on GitHub
  * Choose Node under the gitignore settings when creating a repo
  * Choose to create a README.md file
1. Clone it to your computer using either a terminal command or SourceTree
1. Set up your [file and folder structure](#file-and-folder-structure)
1. Open a terminal window in your repo folder (or use the Terminal button when you open the repo in SourceTree)
1. Run `npm init` in your terminal to create a `package.json` file
  * Set your initial version to `0.1.0` (see also [version numbering](#version-numbering))
  * For open source projects choose an MIT license by typing `MIT` when prompted for a license name
1. Run `atom .` in your terminal to launch Atom in your project folder

[(back to top)](#contents)

## File and folder structure
### Goal
Set up a file and folder structure that lets you add more complexity later, such as build and test systems.
### Solution
1. Create two subfolders:
  1. `src`: place all your source code here
  1. `test`: place all testing code here
1. Create a file in the `src` sub-folder called `index.js`

[(back to top)](#contents)

## Coding style
### Goal
Develop a coding style that lets you share your code without embarrassment.

A sloppy coding style reflects poorly on you.
### Solution
Follow [Airbnb's Javascript Style Guide](https://github.com/airbnb/javascript)

[(back to top)](#contents)

## Native modules and Windows
### Goal
Fix errors related to `node-gyp` when you try to install an npm package.

The problem is due to non-JavaScript code in the package, which npm tries to build on your computer. You will get errors unless you have the build environment installed.
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

[(back to top)](#contents)

# Web
Read this if you are trying to build a web application.

## Technology stack
### Goal
Choose a technology stack (e.g. server framework, database, front-end framework, hosting platform).
### Solution
* Back-end:
  * Hosting: [Heroku](https://www.heroku.com/) (choose the "free dyno" option)
  * Server framework: [express](https://www.npmjs.com/package/express)
  * Sockets: [socket.io](https://www.npmjs.com/package/socket.io)
  * Database: PostgreSQL (host it on Heroku with the free option)
  * Object-relational mapping: [Sequelize](https://www.npmjs.com/package/sequelize)
* Front-end
  * Domain: [Namecheap](https://www.namecheap.com/domains/registration.aspx)
  * Hosting: [Namecheap](https://www.namecheap.com/hosting/shared.aspx)
    * (seeking free CDN suggestions that support custom domains)
  * JavaScript: [React](https://facebook.github.io/react)
    * Use [react-slingshot](https://github.com/coryhouse/react-slingshot) as a template. It sets up a project structure, an example app, and [Redux](https://github.com/reactjs/redux) as a state management system
  * Styling: [Bootstrap](http://getbootstrap.com/)

[(back to top)](#contents)

# Mobile
This section covers problems commonly encountered with:
* developing and distributing native mobile applications in JavaScript
* serving mobile users for web applications

I am seeking contributors for this section.

[(back to top)](#contents)

# Desktop
This section covers problems commonly encountered with developing and distributing desktop applications.

I am seeking contributors for this section.

## Multi-OS framework
### Goal
Package and run your Node.js app as a desktop application on any operating system (OS).
### Solution
Use [Electron](http://electron.atom.io/). It is now considered stable as version 1 was released on May 11, 2016. It is backed by the makers of GitHub and Atom, and has a strong community. Electron apps build and run on Mac, Windows, and Linux.

[(back to top)](#contents)

# Packages
This section covers problems commonly encountered with developing and publishing reusable packages.

## Version numbering
### Goal
Update version numbers in a way that indicates how significantly the package has changed for its users
### Solution
Use [Semantic Versioning](http://semver.org/) (a.k.a. semver).

- Increment your patch (0.0.x) version with `npm version patch`
- Increment your minor (0.x.0) version with `npm version minor`
- Increment your major (x.0.0) version with `npm version major`

Using `npm version` will give you automatic `package.json` version updates, and will also create a git tag for you, that you can simply push with `npm push --tags`.

Here are the most important bits about semver:

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

[(back to top)](#contents)

## Upcoming sections

* General problems
  * understanding event driven programming
  * Clustering (solution: throng)
  * Password hashing (solution: bcrypt)
  * Saving exact and secure dependency versions (solution: --save-exact, --secure, and .npmrc)
  * Good documentation / READMEs
  * Debug logging (solution: debug)
  * Event emitter (solution: eventemitter3)
  * testing
  * user analytics and app monitoring
  * other analytics: keen.io, google analytics and kissmetrics, and key metrics
  * promises and callbacks
  * error handling
* Packages
  * Writing command line tools
  * Publishing to NPM
  * npm publish scripts that update version number for you
* Developing for the web
  * Creating a REST API server (solution: Swagger)
  * Deploying serverless (solution: serverless and AWS Lambda
  * Application architecture (solution: single page apps with a back-end API server)
  * Handling server overload (solution: toobusy)
  * Rate limiting and prevent brute force logins
  * Authentication (solution: jsonwebtoken)
  * don't run your server on port 80 or 443
  * security
  * ssl
  * message queues and async function execution
* Developing mobile applications
  * immediate user feedback for server requests

[(back to top)](#contents)

## Contributing
Contributions are welcome! Here's how you can help:

|If you want to ...|How to contribute|
|---|---|
|Ask for a recommended solution to a particular problem or goal|First, check the [Upcoming sections](#upcoming-sections). We may already be planning to work on it.<br><br>If it isn't listed in the Upcoming sections, please either create a GitHub Issue or send a pull request to add it to the Upcoming sections.|
|Provide a solution to a problem or goal |That's great! Please create a GitHub issue to discuss the solution *before* creating a pull request. Please consider the [criteria for accepting a solution](#how-solutions-were-chosen).|
|Offer a better solution than one already in the Playbook.|Please create a GitHub Issue to discuss this. Consider whether it meets the [criteria for accepting a solution](#how-solutions-were-chosen). Because we are focused on finishing upcoming sections, we are only accepting improvements if they are **vastly** better than the current solution.|

### Acknowledgements
Thanks to the following for helping with ideas and edits

* [aem](https://github.com/aem)
* [antony](https://github.com/antony)
* [Calinou](https://github.com/Calinou)
* [dodekeract](https://github.com/dodekeract)
* [helloworld](https://github.com/helloworld)
* [houjunchen](https://github.com/houjunchen)
* [JTronLabs](https://github.com/JTronLabs)
* [krokofant](https://github.com/krokofant)
* [mateoKaradza](https://github.com/mateoKaradza)
* [Morrisai](https://github.com/Morrisai)
* [NicoPennec](https://github.com/NicoPennec)
* [partounian](https://github.com/partounian)
* [talkahe](https://github.com/talkahe)
* [wli](https://github.com/wli)
* [xxdavid](https://github.com/xxdavid)

[(back to top)](#contents)

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

[(back to top)](#contents)
