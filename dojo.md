# DOJO:

Dojo is JavaScript framework to develop dynamic web applications.
Dojo toolkit will put life in your web application and turn it into highly interactive application. You can turn your web application into desktop like web application.
Dojo offers many widgets, utilities and ajax libraries to develop your application.
Dojo provides higher abstraction layer to the programmer.  So, it helps the programmers to develop powerful functions very easily.

Following are the benefits of Dojo:
===================================

Associative arrays
Loosely typed variables
Regular expressions
Objects and classes
Highly evolved date, math, and string libraries
W3C DOM support in the Dojo


destroy() or destroyRecursive():
================================
Unregister specific widgets, you can use these  methods. The second one destroys any widgets inside the one you are destroying (i.e. calling destroyRecursive on a form widget will also destroy all the form components).

var widgets = dijit.findWidgets(<containerDiv>);
dojo.forEach(widgets, function(w) {
    w.destroyRecursive(true);
});

dojo.require():
==============
In order to use a Dojo module or widget, you have to load the module with dojo.require(‘modulename’). If you don’t do that, your scripts will throw a “dojo.some not defined” or “dojo.some.randomFunction not defined”. 

Dojo’s code is split into modules which are similar to packages in Java except that in Dojo a module can contain both constructors (like classes in Java) and simple functions.

Ex: dojo.require("dojo.dom-style");

require([ 'dojo/dom-style' ], function (domStyle) {
	domStyle.set(txtTACCCodeElement2.domNode, 'display', 'block');
});

dojo.partial():
===============
It’s a function that returns a function. What it does is allow you to fix the first N parameters of a function call to some specific value. This can be very powerful, especially when you want to pass in object references or the like into notification functions of DataStores.

https://dojotoolkit.org/reference-guide/1.6/dojo/partial.html

dojo.byId():
============
This is a simple alias to ’document.getElementById’, which not only is shorter to write, but fortunately works in all browsers. HTML elements "id" attribute is passed to this.

dijit.byId():
=============
It is a little different – first off it only works on parsed dijits either declared in markup with a dojoType attribute or programatically. 
The same id attribute is used as a paramater, but what is returned in this case is an object that was created by the dojo widget system when the markup is parsed and transformed into a dijit. 
This allows you to change dojo-specific attributes for the widget or call methods defined in the class the dijit corresponds to (in this case, we can call methods of the ContentPane class). 
For Example, we can set the content of the ContentPane via setContent().
Ex:
myContentPane = dijit.byId("myDivId");
myContentPane.setContent("Hello World!");

jsId:
=====
With the value passed in this attribute, a global javascript variable is automatically created(the dojo parser does this). This variable contains the same object as returned by dijit.byId(). Whatever value you give to the jsId attribute becomes the name of the global variable so watch out for reserved words or having two widgets with the same jsId!

Ex:
<div id="myDivId" 
     dojoType="dijit.layout.ContentPane"
	 jsId="myJSId"/>

myJSId.domNode.style.height = '300px';
myJSId.setContent("Hello World!");

http://dojocampus.org/content/2008/05/06/jsid-dijitbyid-and-dojobyid/

dojoType:
=========
This attribute is responsible for instructing Dojo on how to process the element when the page is loading. In this case you will use a button element for the button that is used to input element - Dojo will work with either as long as the dojoType attribute is present. If dojoType is not present, then it will be like a normal button.

It adds additional functionality or style to the existing HTML component/element.

Ex:
<button dojoType="Button" widgetId="helloButton" onClick="helloPressed();">Hello World!</button>

_hasResource:
=============
Checks whether a module is available. Its added during build. Do not use _hasResource directly in your code.

function init()
  {
  var helloButton = dojo.widget.byId('helloButton');
  dojo.event.connect(helloButton, 'onClick', 'helloPressed')
  }

  dojo.addOnLoad(init);

dojo.mixin()
============

dojo.mixin is a simple utility function for mixing objects together. 
Mixin combines two objects from right to left, overwriting the left-most object, and returning the newly mixed object for use. 
Dojo mixin is very similar to dojo.extend but only works on objects, whereas extend explicitly extends an object.prototype.

          // Dojo < 1.7
          var a = { b:"c", d:"e" };
          dojo.mixin(a, { d:"f", g:"h" });
          console.log(a); // b:c, d:f, g:h

dojo.extend()
=============
Dojo extend works much like dojo.mixin, though works directly on an object’s prototype. Following the same pattern as mixin, dojo.extend mixes members from the right-most object into the first object, modifying the object directly.

       // Dojo < 1.7
       dojo.require("dijit.TitlePane");
       dojo.extend(dijit.TitlePane, {
          randomAttribute:"value"
       });
      
      
dojo.connect()
==============
dojo.connect is the core event handling and delegation method in Dojo. 
It allows one function to “listen in” on the execution of any other, triggering the second whenever the first is called. 
Many listeners may be attached to a function, and source functions may be either regular function calls or DOM events.
The return value is a handle that is needed to remove this connection with dojo.disconnect.

        // Dojo < 1.7
        dojo.connect(obj, event, context, method, dontFix);
