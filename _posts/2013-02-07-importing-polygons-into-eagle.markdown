---
layout: post
title: "Importing polygons into Eagle"
date: 2013-02-07 20:57
comments: true
categories: eagle
---

Surprisingly often, I find myself wanting to import vector images into eagle, and have them appear as polygons - usually for silkscreen. Whilst importing vectors as lines is practical - although ridiculously awkward - up until now I haven't found a single practical way to import a vector drawing as polygons.

That changed recently when I stumbled across Cruz Monrreal II's [svg2poly](https://github.com/cmonr/Eagle-ULPs). svg2poly is an Eagle ULP that, within the scope of its limitations, does a very good job of importing vector shapes into Eagle. Getting it working was a revelation - I no longer have to mess with awful bitmap imports that arrive as a huge series of tiny rectangles, or spend hours tracing things.

![](http://i.imgur.com/QVwlVn7.png)

<!-- more -->

The main limitation is not one of svg2poly as much as it is one of Eagle: Eagle doesn't support 'hollow' polygons. Cruz provides a workaround for this by showing you how to split closed shapes in an SVG, turning one hollow polygon into two non-hollow ones.

The second limitation is that it doesn't handle curves; the documentation on the svg2poly page also describes how to get around that, by interpolating curves into a series of straight lines.

The docs are pretty clear; the only thing I'd add is that if you still get coarse lines after following the directions, try an additional 'add nodes' step after you've done everything else. Good luck!
