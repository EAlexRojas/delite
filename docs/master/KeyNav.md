---
layout: default
title: delite/HasDropDown
---

# delite/KeyNav

This is a base class to enable keyboard navigation between the widget's descendants.
Navigation can be performed via arrow keys and HOME/END keys, and also a letter key search.
A List, Tree, or Grid widget could all be subclasses of KeyNav.

To use this base class, the subclass must implement a number of abstract methods.  For LEFT/RIGHT/UP/DOWN arrow key
navigation, implement:

* _onLeftArrow()
* _onRightArrow()
* _onDownArrow()
* _onUpArrow()

These methods are meant to navigate relative to the current node,
so they should operate based on `this.focusedChild`.

In addition, the subclass must:

- Set all descendants' initial tabIndex to "-1"; both initial descendants and any
descendants added later, by for example `addChild()`.
- Define `childSelector` to a function or string that identifies focusable child widgets.
- Define `this.containerNode`.

Also, child widgets must implement a `.focus()` method.

## Example

<iframe width="100%" height="300" src="http://jsfiddle.net/ibmjs/Lbvu2/embedded/" allowfullscreen="allowfullscreen" frameborder="0"></iframe>