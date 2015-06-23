
<html lang="en" class="is-copy-enabled">
  <head>
    <meta charset='utf-8'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="Content-Language" content="en">
    <title>JSONPCrossDomain</title>
  </head>


  <body>
<p>Karma and Jasmine Testing Setup on IntelliJ Idea</p>

<h2><a id="user-content-authors" class="anchor" href="#authors" aria-hidden="true"><span class="octicon octicon-link"></span></a>Authors</h2>

<p>Adarsh Kumar (<a href="mailto:adars99@gmail.com">adars99@gmail.com</a>)</p>

<h2><a id="user-content-download" class="anchor" href="#download" aria-hidden="true"><span class="octicon octicon-link"></span></a>Download</h2>

<p>You clone the project with Git by running:</p>

<pre><code>$ git clone git://github.com/adars99/Jasmine-Setup
</code></pre>
# Karma and Jasmine Testing Setup on IntelliJ Idea

To be able to use Jasmine Testing Framework on IntelliJ Idea IDE, first we need to install Karma Test Runner plugin on IntelliJ Idea.With IntelliJ IDEA IDE, you can run and debug javascript unit tests. Please follow the steps to setup and run javascript unit test cases using Jasmine.

#Step 1: Download and install Node.js
 - Please use this link to install <a href="https://nodejs.org/">NodeJS</a> on your local machine.
 - If you are going to use the command line mode, make sure the following paths are added to the PATH variable:<br/>
    1. The path to the parent folder of the Node.js executable file.
    2. The path to the npm folder.This enables you to launch the Karma test runner and npm from any folder.
    <img src="images/Capture4" width="100" height="100"><br/>
 - Install and enable the NodeJS and Karma repository plugin.
   1. Open IntelliJ Idea IDE, go to File->Settings. Search "Plugins" on the left top search bar.
   2. Click on Install JetBrains Plugin button. 
   <img src="images/Capture1" width="100" height="100"><br />
   3. Search NodeJS on Browse JetBrains Plugins window and click on install NodeJS Plugin button.
   <img src="images/Capture2" width="100" height="100"><br />
   4. Search Karma on Browse JetBrains Plugins window and click on install Karma Plugin button.
    <img src="images/Capture3" width="100" height="100"><br/>
   5. Click on Close and apply button and restart the IntelliJ Idea IDE.
   
#Step 2: Install Karma in a project
 - Launch the embedded Terminal by hovering your mouse pointer over in the lower left corner of IntelliJ IDEA and choosing Terminal from the menu.
### Installation Karma globally
```sh
$ npm install -g karma
```
<img src="images/Capture4" width="100" height="100"><br/>

  - Open the project settings by choosing File->Settings.
  - On the Node.Js and NPM page, click on + side and install Node.JS dependent packages if required.If nothing is available then go to next step.
  <img src="images/Capture5" width="100" height="100"><br/>
 
#Step 3: Configuring Jasmine Testing Frameworks in a Project
- Launch the IntelliJ IDEA embedded Terminal to intal the latest offical verson of jasmine. Use NPM:
### Installation
```sh
$ npm install jasmine-node -g
```

#Step 4: Creating Javascript Unit Tests
 - Create a folder "test" at the same level as the src folder.
 - Configuring Test source root
<img src="images/Capture7" width="100" height="100"><br/>
 - Add TestFile e.g. SearchSuggestTest.js and add the below code in your test file
```sh
describe ("first test suite", function(){
    it ("2 should equal 2", function(){
        expect("2").toBe("2");
    });
    it ("1 should not equal 2", function(){
        expect("1").not.toBe("2");
    });
})
```
#Step 5: Running unit tests on karma
Karma executes unit tests according to a karma.conf.js configuration file which is generated semi-automatically in the interactive mode.
The instruction below ensures successful creation of a consistent configuration file karma.conf.js which in its turn ensures successful execution of the tests in your project.
- Create the package.json file under resource folder. 
```sh
{
    "name": "Dune",
    "version": "0.0.1",
    "devDependencies": {
        "karma": "*",
        "karma-chrome-launcher": "*",
        "karma-firefox-launcher": "*",
        "karma-safari-launcher": "*",
        "karma-jasmine": "*"
    }
}
```
- Run the below command under "C:\Development\Dunes\trunk\resources" to instal the whole setup 
```sh
$ npm install
```
- Go to IntelliJ IDEA Terminal window and type the below command under "C:\Development\Dunes\trunk\resources" to create a karma.conf.js file
```sh
$ karma init karma.conf.js
```
Please folllow this link to setup karma.conf.js file .
https://ymichael.com/2014/05/10/javascript-testing-with-karma-js.html

- Note :If Karma does not start, check the installation: the parent folder or the Karma executable file should be specified in the PATH variable.

#Step 6: Install plugin/extension on the browser to run the test cases
- chrome -Install JetBrain IDE Support extenion for chrome
- Firefox -Install JetBrain IDE Support extenion for firefox
- IE -Install JetBrain IDE Support extenion for IE

#Step 7: Launching unit tests
- To launch the tests according to a run configuration, select the Karma run/debug configuration from the list on the main toolbar. Then click the Run button run.png  to the right of the list.
- The Karma test server starts automatically without any steps from your side. View and analyze messages from the test server in the Karma Server tab of the Run tool window.
- Monitor test execution in the Test Runner tab of the Run tool window as described in Monitoring and Managing Tests.
- 
https://ymichael.com/2014/05/10/javascript-testing-with-karma-js.html
### Tech Support
* [node.Js] - evented I/O for the backend
* <a href="http://karma-runner.github.io/0.10/index.html">Karma</a> - Run and debug unit tests 
* <a href="http://jasmine.github.io/">jasmine</a> - Write javascript unit test cases
* <a href="https://www.jetbrains.com/idea/help/enabling-javascript-unit-testing-support.html">Enable Javascript Unit Testing Support</a> - Enabling javascript unit testing support on IntelliJ IDEA  
* <a href="https://www.jetbrains.com/idea/help/preparing-to-use-karma-test-runner.html">Preparing to use Karma Test Runner</a> - Preparing to use karma test runner on IntelliJ IDEA

      
  </body>
</html>

