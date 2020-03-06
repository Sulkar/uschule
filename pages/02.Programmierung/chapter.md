---
title: Programming
taxonomy:
    category: docs
child_type: docs
---

### Scratch

Discover **Scratch**

[Scratch Website](https://scratch.mit.edu/projects/editor/)

![alt](../images/chrome_s4a4TtTTX8.png)

> Hallo ein Test

----------
Hallo jetzt geht es weiter. Wie könnte man das Problem nun lösen?

>Ich habe leider keine Ahnung, doch würde ich gerne eine neue Datei hinzufügen. 

[MD Grav Reference](https://learn.getgrav.org/16/content/markdown)

Eine Tabelle:

| Name | Klasse | Wohnort |
| ------ | ------ | -|
| Richi | data | München |
| Andi | data | Mering |

```python

#imports:
from os import listdir, rename, path
import csv, sys
from tkinter import Tk
from tkinter.filedialog import askopenfilename, askdirectory

#global variables:
PfadZuDateien = ''
meineDateienGefiltert = []

def filterDateien():
    meineDateien = listdir(PfadZuDateien)
    #removes folders:
    for datei in meineDateien:
        if not path.isdir(path.join(PfadZuDateien, datei)):
            global meineDateienGefiltert
            meineDateienGefiltert.append(datei)

```
