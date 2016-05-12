---
layout: post
title: Rotate the screen on Dell xps
tags: dell xps 13 bash script
categories: blog
excerpt: "A simple script for the dell xps"
---

```bash
#!/bin/bash

STATE="$(xrandr -q|grep eDP|cut -c40-45)"

if [ $STATE == "normal" ]
then
    xrandr -o inverted && xinput set-prop 11 "Device Enabled" 0
else
    xrandr -o normal && xinput set-prop 11 "Device Enabled" 1
fi

exit 0
```
