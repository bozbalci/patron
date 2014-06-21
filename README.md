patron
======

A small Python script that creates a small GTK window containing a button with a label, when pressed, runs the command provided in the arguments. It could be used as a "boss button".

Usage
-----

    usage: patron [-h] [-l LABELS [LABELS ...]] [-w WIDTH] commands [commands ...]
    
    Small GTK button that runs a command when pressed.
    
    positional arguments:
      commands              commands to run
    
    optional arguments:
      -h, --help            show this help message and exit
      -l LABELS [LABELS ...]
                            the labels of the button
      -w WIDTH              border width of the window
    
    For alternating commands/labels on each press, provide multiple
    commands/labels. Happy slacking!

Examples
--------

    # Return to the first workspace when the button is clicked, and to the
    # second one when clicked again
    patron 'bspc desktop -f "^1"' 'bspc desktop -f "^2"' -l 'Work!' 'Slack!'
    
    # Mute all sounds when the boss is near, and blast it off when he's away (FreeBSD)
    patron 'mixer -s vol 0' 'mixer -s vol 100' -l 'mute!' 'PARTY TIME!!' -w 10 
   
    # Take a screenshot of the screen
    patron -l 'Scrot' 'scrot unix.png'

Tips
----

* Set this window sticky and always on top, from your window manager's configuration. So the window always stays visible and will be visible on every workspace.
* Don't forget to add a label to each of your commands, or you may forget which command was used the most recently!
* Always have other measures, don't rely on this script alone! I don't take any responsibility if you are caught procrastinating!

Requirements
------------
* Tested on Python 2.7.6
* pygtk
* setproctitle

License
-------

    Copyright (c) 2014, Berk Özbalcı
    All rights reserved.
    
    Redistribution and use in source and binary forms, with or without modification,
    are permitted provided that the following conditions are met:
    
    * Redistributions of source code must retain the above copyright notice, this
      list of conditions and the following disclaimer.
    
    * Redistributions in binary form must reproduce the above copyright notice, this
      list of conditions and the following disclaimer in the documentation and/or
      other materials provided with the distribution.
    
    THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND
    ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
    WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
    DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE FOR
    ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
    (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
    LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON
    ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
    (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
    SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
