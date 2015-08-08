# DrawerCSS

This is a simple JavaScript implementation to create a drawer element, by using CSS3.

# Sample

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
DrawerCSS(base_id:String, drawer_id:String, options?:Hash) | create an instance

Note: If the element of *drawer_id* does not exist, it is created. And it is possible to get the element by `getElementDrawer` instance method.

## Options

property | type | description
---------|------|------------
side | constant | side of the drawer. *TOP*, *RIGHT*, *BOTTOM* or *LEFT*. defalut is *LEFT*
span | string | span of the drawer pane. default is *80%*
effect | constant | effect of the base pane when open. *slide* or *compress*. default is *slide*
duration | float | transition duration. default is *0.3*
delay | float | transition delay. default is *0.0*
timingFunction | constant | transition timing function. default is *ease-in-out*

## Methods

method | return value | description
-------|--------------|------------
destroy()| None | reset CSS properties were changed by this instance
getElementBase() | Element | get the base element
getElementDrawer() | Element | get the drawer element
isOpened() | boolean | return *true* if the drawer is opened, or *false*
open() | this | open the drawer
close() | this | close the drawer
toggle() | boolean | open or close the drawer. it returns *true* if open, or *false*
addHandler(name:String, handler:Function) | this | add *handler* to the *name* event

## Events

name | description
-----|------------
open | fired when open
close | fired when close

# Copyright and license

    DrawerCSS
      Copyright 2015 WATANABE Hiroaki
      Released under the MIT license
