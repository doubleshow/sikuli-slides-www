---
layout: docs
title: GUI
prev_section: recorder
next_section: cmd
permalink: /docs/gui/
---

The simplest method to execute a `.pptx` file is to use the Windows Explorer or Mac's Finder. First you find a file. Then you use "open with" and select Sikuli Slides as the viewing program instead of the default program such as Microsoft Powerpoint. Once the file is opened, the actions described in the file will be executed by Sikuli Slides.

Before you can open and execute slides, you must install Sikuli Slides on your system. If have not already done so, please go to the [Download](/download/) page to download an installer for your system and run it.

## Windows Explorer

1. Locate the `.pptx` file you want to execute. 

2. Do "Open With"

3. Select "Sikuli Slides" instead of Microsoft Powerpoint.

{% include figure.html src="/img/gui_win0.png" %}   

Or if you do not see "Sikuli Slides" as an option, please follow this [instruction](/docs/gui/win) to associate `.pptx` files with Sikuli Slides.

## MacOSX Finder

1. Locate the `.pptx` file you want to execute. 

2. Do "Open With"

3. Select "Sikuli Slides ({{slides.version}})" instead of Microsoft Powerpoint.

{% include figure.html src="/img/gui_mac_finder.png" %}   

Or if you do not see "Sikuli Slides" as an option. Click "Others..." and choose it from the "Applications" folder.

{% include figure.html src="/img/gui_mac_finder_other.png" %}   

Your slides should be executed now.


