# DrawerCSS

This is a simple JavaScript implementation to create a drawer element, by using CSS3.


# Demonstration

[http://hiroaki.github.io/projects/drawercss/sample-advanced.html](http://hiroaki.github.io/projects/drawercss/sample-advanced.html)


# Sample Code

```
<!DOCTYPE html>
<html><head><title>DrawerCSS</title>
<script src="drawer-css.js"></script>
<style>
#container { width:240px; height:120px; background-color:lightblue; overflow: auto; }
#contents {  background-color:lightgreen; }
#menu { overflow: auto; }
</style>
</head><body onclick="drawer.toggle();">
  <div id="container">
    <div id="menu">
      <h1>menu</h1>
      <ul>
        <li>one</li>
        <li>two</li>
        <li>three</li>
      </ul>
    </div>
    <div id="contents">
      <h1>DrawerCSS</h1>
      <p>contents</p>
    </div>
  </div>
  <script>
    drawer = new DrawerCSS('contents', 'menu');
  </script>
</body></html>
```

# API reference


## Constructor

constructor | description
------------|------------
DrawerCSS( base_id:String, drawer_id:String, options?:Hash ) | Create an instance

If the element of *drawer_id* does not exist, it is going to be created. And it is possible to get its element by `getElementDrawer` instance method.


## Options

property | type | description
---------|------|------------
side | constant | Side of the drawer. *TOP*, *RIGHT*, *BOTTOM* or *LEFT*. Defalut is *LEFT*
span | string | Span of the drawer pane. Default is *80%*
maxSpan| string | Limit of `span`, it is available when `span` is specified with "px" or "%". Default is *null* which means unlimited
effect | constant | Effect of the base pane when open. *slide* or *compress*. Default is *slide*
duration | float | Transition duration. Default is *0.3*
delay | float | Transition delay. Default is *0.0*
timingFunction | constant | Transition timing function. Default is *ease-in-out*

The value of `maxSpan` is available in these cases:

* `maxSpan` specified with "%" when `span` is "px"
* `maxSpan` specified with "px" when `span` is "%"

Other cases are not supported.


## Methods


### Class Methods

method | return value | description
-------|--------------|------------
getDimensions( el:Element ) | Hash | Return dimensions of the *el* like as `{width: px, height: px}`


### Instance Methods

method | return value | description
-------|--------------|------------
destroy( )| None | Reset CSS properties were changed by this instance
getElementBase( ) | Element | Get the base element
getElementDrawer( ) | Element | Get the drawer element
isOpened( ) | boolean | Return *true* if the drawer is opened, or *false*
open( ) | this | Open the drawer
close( ) | this | Close the drawer
toggle( ) | boolean | Open or close the drawer. It returns *true* if open, or *false*
addHandler( name:String, handler:Function ) | this | Add *handler* to the *name* event. See also "Events" section below.


## Events

name | description
-----|------------
open | It is going to be fired when the drawer opens
close | It is going to be fired when the drawer closes


# Copyright and license

    DrawerCSS
      Copyright 2015 WATANABE Hiroaki
      Released under the MIT license
