Activator Manual README

This repo stores all the Activator Manual pages in the folder of /pages. The manual is published at [http://kgrid.org/ActivatorManual](http://kgrid.org/ActivatorManual).

To add new pages, simply edit your content and save the md file in the folder of pages. The file name should follow the naming convention so that it will show up at the correct position with the navigation menu.


File Name convention

The file of manual page is named starting with the chapter number, section number, page number followed by regular text. An example is shown below:

```
01-02-01-getting_started.md
```


Jekyll build instruction

At the beginning of the md file, make sure include the following segment for Jekyll build instruction

```
---
layout: page
title: Get Started
level: 1
permalink: /getting_started/
---
```

`layout` should stay with `page`;

`title` will supply the text used in the navigation menu for this page;

`level` indicates the indent level. 0 for no indent while higher number for more indent (currently 2 is the highest possible);

`permalink` will allow Jekyll to build the proper URL link for the page.
