Dev Tools Example
=================

A quick example for how we'll use the Chrome DevTools while at Prime.

Ways to open DevTools:
From the Chrome menu
![alt tag](pics/00 openFromMenu.png)
Right-click on the page and choose "inspect" (My preferred method)
![alt tag](pics/01 openFromRtClick.png)

"Elements" offers a lot of help on front end and visual work. When highlighting elements in this tab they also highlight on the DOM
![alt tag](pics/02 elements.png)

"Sources" shows what files are linked to the current document and where they are located. In this simple project we can see the js file in the "scripts" folder and the css file in the "styles" folder.
![alt tag](pics/03 sources.png)

"Console" is where we'll be doing much of our work. As you've seen, "console.log()" puts text in the Console and this is one of the most useful tools in your Batman Utility Belt.
![alt tag](pics/04 console.png)

Let's take a gander at the code within this project. You'll see that there's a couple global variables (globalNumber, globalString) and a "startMeUp" function that is run on page load. There are also functions for "showGlobals", "someMathyThing", and "someWordyThing".

I've tried to comment the code meaningfully so you should be able to glean it's functionality by mindfully perusing the JS file. The "startMeUp" function is run on page load via the "onLoad" tag in the body element. This can be seen in the Elements tab of DevTools:
![alt tag](pics/05 onLoad.png)

Elements can be expanded via their handles in the Elements window.
![alt tag](pics/06 elementExpand.png)

Below we can see the output of the console when this project is run when in its working state:
![alt tag](pics/07 consoleOutput.png)

A few practices that I've adopted that may not be self-explanatory:
* I prefer to keep things in alphabetical order when possible. This helps me locate function/variables and the like easier/faster. Note that there are times when the order in which operations are done will break this preference.
* I like to minimize white space. The only time I'll leave an empty line is before a function declaration. Any other "non-code" space is usually a comment.
* the first console.log in the JS file that alerts that the script has been sourced isn't necessary, but can be helpful when sourcing a number of files and you need to know the order in which they are sourced. This is can be helpful later on.
* Logging out the entry point to a function (the 'in FUNCTIONNAME' log that I do on the first line of each function)is likewise not necessary, but I find it a useful practice when tracing through the console.

Using the console to trouble shoot
==================================
Let's look at what happens when there's problems with the code:
![alt tag](pics/08 errors.png)

Here, we've got a couple errors. We can see the first error points to our JS file and ends with an "ERR_FILE_NOT_FOUND" message. The second error says that the 'startMeUp' function cannot be found.
If we look a the far right of the error messages we'll see that they are on lines 7 and 9 of index.html. By expanding the second error we can see that it is in the "onload" call of line 9 of index.html.

A quick look at our Sources tab also shows that the JS file is not linked.
![alt tag](pics/09 sourceMissing.png)

On line 7 in index.html:
![alt tag](pics/10 errorLine.png)
Here we can see the HTML file is trying to source in "scripts.js". Problem is that the file is named "script.js".

Once that is fixed, we'll be able to see the script correctly sourced again:
![alt tag](pics/11 sourceCorrected.png)

Awesome! Except it looks like we've got another error now:
![alt tag](pics/12 newError.png)


Your assignment:

Regular mode:
* ID and fix this error
* Email us how you found it and what you had to do.
* zip file download: https://github.com/devjanaprime/devToolsExample/archive/master.zip

Hard mode:
* Do the same for this
* explain each of the errors you found and how they were fixed
* zip file download: https://github.com/devjanaprime/devToolsExample/archive/iHaveIssues.zip

Contrary to popular belief, DevTools was not named after me.
