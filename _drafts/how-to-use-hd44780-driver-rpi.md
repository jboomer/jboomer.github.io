---
layout: post
title: How to use the HD44780 LCD driver with a raspberry pi
tags: [ rpi, linux ]
---

# The HD44780 

Stuff about this thing

# Using the overlay

Stuff here

{% highlight c %}

/dts-v1/;
/plugin/;
/ {
    compatible = "brcm, bcm2708";

    fragment@0 {
        target-path = "/";
        __overlay__ {
            // Creates an auxdisplay node with label  "lcd-screen"
            lcd_screen: auxdisplay {
                compatible = "hit,hd44780";

                data-gpios = <&gpio 6 0>,
                             <&gpio 13 0>,
                             <&gpio 19 0>,
                             <&gpio 26 0>;
                enable-gpios = <&gpio 21 0>;
                rs-gpios = <&gpio 20 0>;

                display-height-chars = <2>;
                display-width-chars = <16>;
            };

        };
    };
{% endhighlight %}

# Changing the pins

How to set the params

# Default messages

Use the parellel port auxdisplay settings

# Custom characters

Weird escape codes
