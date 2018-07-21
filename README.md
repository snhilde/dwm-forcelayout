# dwm-forcelayout
This patch for [dwm](https://dwm.suckless.org/) forces a tag to stick to a certain layout. This is handy for automatically switching at launch time to a layout other than the default for tabs that have applications pinned to them, like tab 9 and firefox. It just makes the experience that much more seamless so you can focus on the real work. Of course, this assumes you are following the tags-as-workspaces paradigm, like I do. Don't tell the [lead developer of dmenu](http://web.archive.org/web/20120120161931/http://lubutu.com/rant/dwm-faq).

## Installation
The patch assumes a fresh copy of dwm. Beyond that, you may have to edit the source code by hand.
In the root directory, run this command:
```
patch -b < /path/to/patch.diff
```
That's it. If anything failed, then fire up your preferred editor and get those hands dirty.

## Configuration
I highly recommend using this patch with the [pertag patch](https://dwm.suckless.org/patches/pertag/). These two together really implement a strong workspace flow within dwm. 
To force specific tags to arrange according to specific layouts, you will need to edit the `taglayouts` array in `config.def.h` (or `config.h` if you're already going). Here is the definition with one example included:
```
static const Taglayout taglayouts[] = {
	/* tag		layout */
	{ 9,		{.v = &layouts[2]} },
};
```
This forces tag 9 to arrange according to layout 3 (C arrays begin numbering at 0) of the `layouts` array. Add or edit your rules from here.

### Author
Hilde N.
