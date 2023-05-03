Download Link: https://assignmentchef.com/product/solved-cs142-project2-javascript-calisthenics
<br>
Although this project has you run code in your browser, you need to have Node.js installed on your system to run the code quality checker. If you haven’t already installed Node.js and the npm package manager, follow the <a href="https://web.stanford.edu/class/cs142/install.html">installation instructions (install.html) </a>now.

Once you have Node.js installed, create a directory project2 and extract the contents of <a href="https://web.stanford.edu/class/cs142/downloads/project2.zip">this zip le (downloads/project2.zip) </a>into the directory. The zip le contains the les cs142-test-project2.html and cs142-test-project2.js that act as a testing framework for the code you write in this project.

You can fetch the code quality tool, <a href="http://jshint.com/about">JSHint (http://jshint.com/about)</a>, by running the following command in the project2 directory:

This will fetch JSHint into the node_modules subdirectory. You will be able to run it on all the JavaScript les in project2 directory by running the command:

The code you submit should start with “use strict”; in each JavaScript le and running JShint should not output any warnings. <strong>Any warnings will be used to deduct style points.</strong>

To run the assignment open the le cs142-test-project2.html in your browser. The web page will load the JavaScript and run a few tests. Since Node.js also contains a JavaScript virtual machine you can also run the tests without a browser using the command:

The JavaScript development environment is much better in the browser so we suggest you do your development using it.

<strong>Note:</strong> These tests don’t cover all the edge cases. They are there to help guide you and let you know when you have the basic functionality. It is your responsiblity to handle everything stated in the following specs that aren’t explicitly tested in the test le we give you.

In this project we ask you to write or modify some JavaScript functions. The problems in this assignment are of a practical nature and functionality you develop will be useful in completing later class projects. Given the availability of JavaScript libraries to solve or help solve pretty much any JavaScript tasks you would be assigned, it is likely you could solve these with a couple of lines to call some library routine. Since the goal of the project is to learn JavaScript, <strong>we forbid you to use any JavaScript libraries in your solutions.</strong> Functions built-in to JavaScript Arrays and Date objects are acceptable.

<h1> Problem 1: Generate a Multi Filter Function (10 points)</h1>

In your project2 directory, make a new le named cs142-make-multi-filter.js .The code for your Multi Filter Function will go in this le.

Declare a global function named cs142MakeMultiFilter that takes an array ( originalArray ) as a parameter and returns a function that can be used to lter the elements of this array. The returned function ( arrayFilterer ) internally keeps track of a notion called currentArray . Initially,

currentArray is set to be identical to originalArray . The arrayFilterer function takes two functions as parameters. They are:

<ol>

 <li>filterCriteria – A function that takes an array element as a parameter and returns a boolean. This function is called on every element of currentArray and currentArray is updated to re ect the results of the filterCriteria If the filterCriteria function returns false for an element, that element should be removed from currentArray . Otherwise, it is left in currentArray . If filterCriteria is not a</li>

</ol>

function, the returned function ( arrayFilterer ) should immediately return the value of currentArray with no ltering performed.

<ol start="2">

 <li>callback – A function that will be called when the ltering is done. callback takes the value of currentArray as an argument. Accessing this inside the callback function should reference the value of originalArray . If callback is not a function, it should be ignored. callback</li>

</ol>

does not have a return value.

The arrayFilterer function should return itself unless the filterCriteria parameter is not speci ed in which case it should return the currentArray . It must be possible to have multiple arrayFilterer functions operating at the same time.

The following code shows how one might make use of the functions you de ne in this problem:

In your project2 directory, make a new le named cs142-template-processor.js . The code for your Template Processor will go in this le.

Create a template processor class ( Cs142TemplateProcessor ) that is constructed with a string parameter template and has a method fillIn . When invoked with an argument of a dictionary object, fillIn returns a string with the template lled in with values from the dictionary object. Cs142TemplateProcessor should be written using the standard JavaScript constructor and prototype structure.

<table>

 <tbody>

  <tr>

   <td width="11"></td>

  </tr>

  <tr>

   <td></td>

   <td></td>

  </tr>

 </tbody>

</table>

The fillIn method returns the template string with any text of the form {{property}} replaced with the corresponding property of the dictionary object passed to the function.

If the template speci es a property that is not de ned in the dictionary object, the property should be replaced with an empty string. If the property is between two words, you’ll notice that replacing the property with an empty string will result in two consecutive whitespaces. Example: “This {{undefinedProperty}} is cool” -&gt; “This  is cool” . This is ne. You do not have to worry about getting rid of the extra whitespace.

Your system need only handle properly formatted properties. Its behavior can be left unde ned in the following cases as we will not be checking explicitly for them.

<h1>Problem 3: Fix cs142-test-project2.js to not pollute the global namespace (5 points)</h1>

The test JavaScript le we give you ( cs142-test-project2.js ) declares numerous symbols in the global JavaScript namespace. For example, after the script is loaded the symbol p1Message appears in the global namespace. Another JavaScript le would then be able to access and change p1Message . Change cs142-test-project2.js to use the standard JavaScript module pattern using an <strong>anonymous function</strong> to hide symbols in the global namespace yet keep the same checking functionality.

Style Points (5 points)

These points will be awarded if your JavaScript code for the problems above is clean, readable, and JSHint warning-free.

<h1>Useful Hints</h1>

In JavaScript, the convention for checking equality/inequality is === and !== , instead of == and != .

When running JSHint, make sure the .jshintrc (hidden le) is present, or JSHint will throw an error. You can use the command ls -a to view all the les in your current directory, including hidden les.

When moving les around, make sure to do that using the command line. Dragging/dropping les usually does not move hidden les which is a common reason for students missing their .jshintrc le.

The requirement that your solution to Problem 2 support multiple simultaneous uses of cs142MakeMultiFilter means that you should not be using global variables to store the currentArray state.

In problem 3, you only need to address symbols created by the test le. Also, you will need to leave the variable cs142Project2Results as a global (i.e., property on the window object) so that you can continue to run the tests using the run-tests-using-node.js script.

<h1> Deliverables</h1>

Use the standard class <a href="https://web.stanford.edu/class/cs142/submit.html">submission mechanism (submit.html)</a> to submit the project2 directory. This directory should include the starter les we gave you along with code les you created or modi ed for the problems including cs142-make-multi-filter.js , cs142-template-processor.js , cs142test-project2.js , and cs142-test-project2.html . Make sure your submission runs npm run jshint and npm test with no errors.

Designed by Raymond Luong for CS142 at Stanford University

Powered by <a href="https://getbootstrap.com/">Bootstrap (http://getbootstrap.com/) </a>and <a href="https://jekyllrb.com/">Jekyll (https://jekyllrb.com)</a> – <a href="https://web.stanford.edu/class/cs142/website.html"><strong>learn more</strong></a><a href="https://web.stanford.edu/class/cs142/website.html"> (website.html)</a>