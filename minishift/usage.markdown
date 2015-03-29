---
layout: page-side
title: "Minishift usage"
date: 2014-04-03 20:47
comments: true
sharing: true
footer: true
section: minishift
---

## Installation

To control the minishift from your computer, you'll first have to install the minishift library. Make sure you have python 2.7 and [pip installed](http://pip.readthedocs.org/en/latest/installing.html), then install the minishift library:

    $ pip install minishift-python

or, to install from source:

    $ git clone https://github.com/arachnidlabs/minishift-python.git
    $ cd minishift-python
    $ sudo setup.py install

The minishift library should work on Linux, OSX, and Windows.

## Usage - HTTP interface

The minishift module ships with a daemon that implements a simple HTTP API for controlling the minishift. You can start the daemon like so:

    $ python -m minishift.minishiftd width

where `width` is the number of horizontal pixels in your chain of minishifts - for example, 32 in a 4-module minishift array.

Optionally, you can run minishiftd as a background daemon:

    $ python -m minishift.minishiftd -d width

By default minishiftd listens on port 8000; you can configure this with the -p argument:

    $ python -m minishift.minishiftd -p 8001 width

Once the daemon is running, you can set the text by making POST or GET requests to the `/set/` endpoint:

    $ curl -G http://localhost:8000/set --data-urlencode "text=Test!"

To display scrolling text, supply the `interval` parameter, which specifies the number of seconds to scroll one pixel. You can also supply the optional `times` parameter, to display the message a fixed number of times before going blank:

    $ curl -G http://localhost:8000/set --data-urlencode "text=To be or not to be, that is the question" -d interval=0.05 -d times=2

## Usage - Python library

The minishift module also provides a Python library. More complete documentation is [in the readme](https://github.com/arachnidlabs/minishift-python/blob/master/README.md), but basic usage looks something like this:

    >>> import minishift
    >>> vid, pid, width = 0x04d8, 0xf517, 32
    >>> ms = minishift.Minishift(minishift.MCP2210Interface(vid, pid), width)
    >>> ms.canvas.write_text(0, "Test!")
    >>> ms.update()
