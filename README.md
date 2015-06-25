
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

To be able to use Jasmine Testing Framework on IntelliJ Idea IDE, first we need to install Karma Test Runner plugin on IntelliJ Idea.With IntelliJ IDEA IDE, you can run and debug javascript unit test cases.
Please follow the below steps to setup and run jasmine javascript unit test cases using karma on IntelliJ IDEA.

#Step 1: Download and install Node.js
 - Please use this link to install <a href="https://nodejs.org/">NodeJS</a> on your local machine. We need node as Karma and Jasmine are based on NodeJS.
 - If you are going to use the command line mode, make sure the following paths are added to the PATH variable:<br/>
    1. The path to the parent folder of the Node.js executable file.
    2. The path to the npm folder.This enables you to launch the Karma test runner and npm from any folder.
    <img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture4.PNG"><br/>
 - Install and enable the NodeJS and Karma repository plugin.
   1. Open IntelliJ Idea IDE, go to File->Settings. Search "Plugins" on the left top search bar.
   2. Click on Install JetBrains Plugin button. 
  <img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture1.PNG"><br />
   3. Search NodeJS on Browse JetBrains Plugins window and click on install NodeJS Plugin button.
   <img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture2.PNG"><br />
   4. Search Karma on Browse JetBrains Plugins window and click on install Karma Plugin button.
    <img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture3.PNG"><br/>
   5. Click on Close and apply button and restart the IntelliJ Idea IDE.
   
#Step 2: Install Karma in a project and globally
 - Launch the embedded Terminal by hovering your mouse pointer over in the lower left corner of IntelliJ IDEA and choosing Terminal from the menu.
### Installation Karma globally by running the below command
```sh
$ npm install -g karma
```
<img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture5.PNG"><br/>

  - Open the project settings by choosing File->Settings.
  - On the Node.Js and NPM page, click on + side and install Node.JS dependent packages if required.If nothing is available then go to next step.
  <img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture6.PNG"><br/>
 
#Step 3: Configuring Jasmine Testing Frameworks in a Project
- Launch the IntelliJ IDEA embedded Terminal to install the latest official version of jasmine.

### Installation - Use NPM
```sh
$ npm install jasmine-node -g
```

#Step 4: Configuring karma coverage in a Project
- Launch the IntelliJ IDEA embedded Terminal to install the latest official version of karma-coverage.
- Please copy/paste karma.conf.js file or check below  steps to setup karma-coverage.

### Installation - Use NPM
```sh
$ npm install karma karma-coverage --save-dev
```

### Code Coverage setup on karma.conf.js file 
```sh
    preprocessors: {
        'UnitTest/js/common/**/*.js': ['coverage']
    },
	 reporters: ['progress', 'coverage'],
      coverageReporter: {
          dir : 'output/coverage/',
          reporters: [
              // reporters not supporting the `file` property
              { type: 'html', subdir: 'report-html' },
              { type: 'lcov', subdir: 'report-lcov' },
              // reporters supporting the `file` property, use `subdir` to directly
              // output them in the `dir` directory
              { type: 'cobertura', subdir: '.', file: 'cobertura.txt' },
              { type: 'lcovonly', subdir: '.', file: 'report-lcovonly.txt' },
              { type: 'teamcity', subdir: '.', file: 'teamcity.txt' },
              { type: 'text', subdir: '.', file: 'text.txt' },
              { type: 'text-summary', subdir: '.', file: 'text-summary.txt' },
          ]
      }
```

#Step 5: Creating JavaScript Unit Tests
 - Create a folder "test" at the same level as the src/static folder.
 - Create a UnitTest and FuntionalTest folder under test folder to add unit test and functional test cases.
 - Configuring Test source root
<img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture7.PNG"><br/>
 - Add TestFile e.g. SearchSuggest.Test.js and add the below code in your test file to test the jasmine test cases.
 
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

#Step 6: Running unit tests on karma
Karma executes unit test cases according to a karma.conf.js configuration file which is generated semi-automatically in the interactive mode.
<br/>
The instruction below ensures successful creation of a consistent configuration file karma.conf.js which in its turn ensures successful execution of the tests in your project.<br/>

- Create the package.json file under test folder. 

```sh
{
    "name": "applicationName",
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

- Run the below command under e.g. "C:\Development\Dunes\trunk\resources\test" to install the whole setup 

```sh
$ npm install
```
- Go to IntelliJ IDEA Terminal window and type the below command under e.g. "C:\Development\Dunes\trunk\resources\test" to create a karma.conf.js file

```sh
$ karma init karma.conf.js
```

- Copy and paste the attached karma.conf.js and test-main.js files under test folder

- Note :If Karma does not start, check the installation: the parent folder or the Karma executable file should be specified in the PATH variable.

#Step 7: Configuring Karma on IntelliJ  IDEA
<img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture8.PNG"><br/>

#Step 8: Optional Install plug-in/extension on the browser to debug the test cases if required
- chrome -Install JetBrain IDE Support extenion for chrome
- Firefox -Install JetBrain IDE Support extenion for firefox
- IE -Install JetBrain IDE Support extenion for IE

#Step 9: Launching unit tests
- To launch the tests according to a run configuration, select the Karma run/debug configuration from the list on the main toolbar. Then click the Run button to the right of the list.

OR

- Go to IntelliJ IDEA Terminal window and type the below command under e.g. "C:\Development\Dunes\trunk\resources\test" 

```sh
$ karma start
```
- In IntelliJ IDEA, click on the test coverage icon. please check the below screenshot

<img src="https://github.com/adars99/Jasmine-Setup/blob/master/images/Capture9.PNG"><br/>

- The Karma test server starts automatically without any steps from your side. View and analyse messages from the test server in the Karma Server tab of the Run tool window.
- Monitor test execution in the Test Runner tab of the Run tool window as described in Monitoring and Managing Tests.


### Tech Support

* [node.Js] - evented I/O for the backend
* <a href="http://karma-runner.github.io/0.10/index.html">Karma</a> - Run and debug unit tests 
* <a href="http://jasmine.github.io/">jasmine</a> - Write javascript unit test cases
* <a href="https://www.jetbrains.com/idea/help/enabling-javascript-unit-testing-support.html">Enable Javascript Unit Testing Support</a> - Enabling javascript unit testing support on IntelliJ IDEA  
* <a href="https://www.jetbrains.com/idea/help/preparing-to-use-karma-test-runner.html">Preparing to use Karma Test Runner</a> - Preparing to use karma test runner on IntelliJ IDEA
      
  </body>
</html>

