.. -*- coding: UTF-8 -*-

:Subtitle: Graphic examples of loving a ListView

.. _samples-label:

Samples
=======

These are examples of what can be done with an `ObjectListView`.

+------------------------------------------+----------------------------------------------+
|                                          |                                             |
| `Foobar Lookalike`_                      | .. image:: images/foobar-lookalike-small.png |
|                                          |   :align: center                            |
| Shows how to creatively use decorations, |                                             |
| and hot item styles.                     |                                             |
|                                          |                                             |
|                                          |                                             |
|                                          |                                             |
+------------------------------------------+----------------------------------------------+
|                                          |                                             |
| `Task List`_                             | .. image:: images/task-list-small.png        |
|                                          |   :align: center                            |
| Shows a more sophisticated renderer as   |                                             |
| well as demonstrating how to combine a   |                                             |
| decoration with a renderer.              |                                             |
|                                          |                                             |
+------------------------------------------+----------------------------------------------+
                                              
                                              
Foobar Lookalike                              
----------------                              
                                              
Those who dwell in the house of cool know that black goes with everything.
                                            
.. image:: images/foobar-lookalike.png      
                                            
A normal ListView cannot display things that exceed the bounds of their cells.
But `ObjectListView` has decorations and overlays so it is much more flexible.
                                            
The dark background is a simple `BackColor` setting. The different colored text
is handled throught a `FormatCell` event. The hot row highlighting is handled
through normal `HotItemStyle` mechanism. The only interesting bit is that it
uses the `LeftColumn` property to limit the cells that are highlighted as hot.
                                            
The clever  bit is  getting the  album artwork  into the  control. This  is done
through two types of decorations. In the first row in an album, cell 0 is  given
an `ImageDecoration` which shows a thumbnail of the artwork. This works, but the
artwork isn't always correctly redrawn:  it's only redrawn properly when  cell 0
is visible.

To get around this  problem, we install proxy  decorations on cell 0  of all the
other rows in the album. These  proxies simply make the artwork decoration  draw
itself. In this way, the artwork is redrawn even when cell 0 of the first row is
not visible.

`Download from here`_

.. _Download from here: http://sourceforge.net/projects

Task List
---------

The Foobar example is cool, but this task list is useful. Displaying this kind
of icon-title-description combination is a common task in many UI situations.

.. image:: images/task-list.png

This sample shows a custom `Decoration` that draws an icon, title and multiline
description.

`ObjectListView` comes with `DescribedTaskRenderer` which is a `Renderer` that
does the same task.

`Download sample project from here`_

.. _Download sample project from here: http://sourceforge.net/projects
