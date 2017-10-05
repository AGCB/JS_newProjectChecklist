# JS_newProjectChecklist
a list of the many things we need to consider when starting a new project in JS

## Editor
* Which one?
* Which plugins?
* Use built-in terminal?
* Editor Config
## Module Format
* ES6 Modules, CommonJS
## HTML Generation
* Minify?
* Use plugin?
* Inject prod only concerns?
* Templating Language?
## Transpiling
* Native ES or diff Language?
* Use experimental features?
* Which plugins?
* Production vs. dev config?
## Bundler
* Webpack, Browserify, Rollup?
## Linting
* Which linter?
* Enable which rules?
* Warning or error?
* Which plugins?
* Use a preset?
## Testing
* Framework?
* Assertion Library?
* Helpers?
* Test File Location?
* File Naming?
* What environment?
* Mocking?
* Code Coverage
* Continuous Integration
## Project Structure
* By file type or feature?
* Centralize API?
* Allow inline JS?
* Extract to POJOs?
## HTTP
* Library
* Mock schema format
* Mock data generation
* Mock Server
## Production Build
* Minification
* SourceMaps
* Bundle Splitting
* Error Logging
* Cache busting
## Automated Deployment

The motivation behind this list is Cory House and his talk at NebraskaJS September 2017 titled
[The Reusable Javascript Revolution](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&ved=0ahUKEwiw_qjc2tjWAhVpzVQKHaBeCLwQtwIIKDAA&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DWrbdNhPhkMM&usg=AOvVaw15pDHcULG_2VlENIYypYb3){:target="_blank"}.
2008 He would throw a bunch of scripts tags into his main file. His workflow would was as follows...

1. Search the Web
2. Read the Docs
3. Download the relevant CSS/JS
4. Setup script tags and style references
5. Write JS that targets HTML element
6. Find a Bug
7. Found an incorrect DOM query
8. Found a Bug
9. Realize his script order was wrong (at this stage you have to keep a lot of complexity in your head)
10. Found a Bug
11. He had to update jQuery version and repeat all steps again.
At this stage there was no minifying or bundling.
Today we have...
1. npm install lib
2. import lib from 'lib'
3. npm update
npm packages fill the gap of JS not having a base library.

Cory's team published Fusion, a framework for React dev at Cox Auto. It's an npm package where the package.JSON has all of their team's dependencies that they use. Developers don't have to make any of these decisions. The package encapsulates Build Scripts, Dev Environment, Lint/Test/Transpiling Config and dependencies. This way the only dependencies devs worry about is updating Fusion. They contain 75 npm packages and opinions into a single dependency?

## The first JS Revolution was NPM
He looks at VanillaJS as malpractice. We should be standing on shoulders of giants to focus on harder problems. He sees file/newProject as malpractice. He points to an analogy of Doctors that use a checklist to make sure that they don't miss anything important. The Checklist Manifesto is a book that drives this point home. Doctors found dramatic results using 
this approach. 

He has a PullRequestTemplate.md which is a code review checklist. He suggests to strive to automate such a process. The more things that we can take for granted the better. His team can start, build, and deploy apps with only 1 command. He has a default 
demo app that gets loaded. Once a dev wants, he can delete the template and go on working. npm remove-demo. 
## Revolution2, the Starter Kit. 
He suggests forking a starter kit and making it your own. He used create-react-app as a starting point. Schedule a meeting with your team about every one of these issues.

## Revolution3, Components
The mental model here is that instead of seeing Separation of Concerns as HTML, JS, and CSS as the three different paradigms to work with, he thinks you should look at a higher level abstraction with Button, DatePicker, Modal, List, List Item, Media, etc. Each of those should have their own HTML/CSS/JS. He sees the problems of the Web Components Standard being already currently solved by modern JS frameworks. He suggests teams need their own reusable component library.

