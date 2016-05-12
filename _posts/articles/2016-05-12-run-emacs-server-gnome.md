---
layout: post
title: Running emacs in daemon mode in Gnome 3
tags: linux emacs gnome3
categories: blog
excerpt: "How to run emacs in daemon mode and use emacsclient in Gnome 3: a simple way to do it."
---

Make a copy of `/usr/share/applications/emacs.desktop` to `/usr/share/applications/emacsclient.desktop`. It looks like this:

```bash
[Desktop Entry]
Name=Emacs
GenericName=Text Editor
Comment=Edit text
MimeType=text/english;text/plain;text/x-makefile;text/x-c++hdr;text/x-c++src;text/x-chdr;text/x-csrc;text/x-java;text/x-moc;text/x-pascal;text/x-tcl;text/x-tex;application/x-shellscript;text/x-c;text/x-c++;
Exec=emacs %F
Icon=emacs
Type=Application
Terminal=false
Categories=Development;TextEditor;
StartupWMClass=Emacs
Keywords=Text;Editor;
```

Modify `Exec=emacs %F` to `Exec=emacs --daemon%F`. Then start Gnome Tweak Tool and enable emacs to start at boot.

Then open `/usr/share/applications/emacsclient.desktop` and change `Exec=emacsclient %F`. Now, right click to a file you would usually open with emacs and select "Open with..." -> "Emacsclient".

Done.
