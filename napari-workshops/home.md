# I2K 2024: Intermediate napari: from exploratory workflow to widgets

**Peter Sobolewski**  
Imaging Applications, Research IT  
The Jackson Laboratory  
napari core developer  


This repository contains materials for the "Intermediate `napari`: from exploratory workflow to widgets" workshop
run at [I2K 2024](https://events.humantechnopole.it/event/1/contributions/58/)

The workshop will involve live coding, showing how one can use a Jupyter notebook for exploratory data analysis in napari and then make simple widgets based on that. For this, magicgui will be introduced as a way to generate widgets quickly and easily. Next, keybinding custom functions will be introduced.

The target is someone who has some familiarity with the napari application and bioimage analysis in Python and wants to take the next steps to customize/extend the napari GUI. 

# From workflow to widget: customizing napari

The napari application uses a backend for the graphical user interface (GUI) called [Qt](https://doc.qt.io). A key feature of this framework is the use of [widgets](https://doc.qt.io/qt-6/qtwidgets-index.html), which are composable, basic UI elements. napari not only utilizes these for its UI, but also enables you can add your own as `dockable` elements. In fact, the layer controls, layer list, and napari console are all such dockable containers of Qt widgets.

There are a number of ways to go about creating your own widgets, you can see [an in-depth overview in the napari documentation](https://napari.org/dev/howtos/extending/magicgui.html). By far the simplest is to rely on the fact that napari supports the use of [`magicgui`](https://pyapp-kit.github.io/magicgui/), a Python library for quick and easy building of GUIs. A key feature of `magicgui` is autogeneration of GUIs from functions and dataclasses, by mapping Python type hints to widgets.

Additionally, napari operates within [an event loop](https://napari.org/stable/guides/event_loop.html#intro-to-event-loop) and users can [connect to native napari events](https://napari.org/stable/howtos/extending/connecting_events.html#hooking-up-your-own-events) to trigger various actions. Importantly, this an enables you to bind key-press events to custom callback functions. Note this is in addition to napari's own extensive keyboard shortcuts that can be customized in the Preferences/Settings GUI.



## Colophon

The material is a part of a prior workshop that was run at JAX, which has more introductory material as well: [https://thejacksonlaboratory.github.io/intro-napari-workshop/](https://thejacksonlaboratory.github.io/intro-napari-workshop/). The basis for the workshop materials was the [`napari-workshops-template` project](https://github.com/napari/napari-workshop-template). 
Some notebooks were removed and reorganized. For information on preparing your own workshop materials using the template, please see [the documentation for the `napari-workshops-template` repository](https://napari.org/napari-workshop-template/docs/build_your_workshop.html).

