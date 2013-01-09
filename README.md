dwmii
=====

I've been using wmii for several years now. Not because it's the best tiling window manager but because its window management fits my needs.

Ever since dwm has been created I've been tempted to switch over. I like most of the philosophy beihind it, but I would have need to apply several patches to get it to work in a way that is sane for my workflow.

I'm too lazy -- or it's not enough of a priority? -- to and fiddle around with the patches each time dwm changes. But if there are a few people that care enough, I would participate in mantaining a dwmii which uses the dwm codebase with the patches that restore the sane part of wmii.

Here are the behaviors from wmii that I miss in dwm:
- the standard wmii layout:
  - Columns width golden ratio width (I have a wide screen!)
  - the win-shift-[hjkl] to move windows where we want
  - each column can maximized, stacked, or in the default state
- tags are dynamically created
- tags can be named
- per tag layout

And here are the parts of wmii (or other WMs) that i don't want to have in dwmii:
- the contextual menu to kill/close the windows (win-shift-c and xkill are more than enough!)
- no filesystem interface (no 9P)

Basically, I still want back my wmi and I also miss the possibility to have tabbed windows.

Some links:
- [dev] wmii as a prepatched dwm: http://lists.suckless.org/dev/1106/8789.html

Existing patches:
- pushup and pushdown provide a way to move clients inside the clients list
  - push: http://dwm.suckless.org/patches/push
  - movestack: http://dwm.suckless.org/patches/movestack
- This patch allows you to change the names of dwm’s tags while it’s running.
  - http://dwm.suckless.org/patches/nametag
- attachabove makes new clients attach above the selected client (instead of always becoming the new master) - basically how Xmonad does it
  - http://dwm.suckless.org/patches/attachabove
- This patch keeps layout, mwfact, barpos and nmaster per tag.
  - http://dwm.suckless.org/patches/pertag
- This patch restores the ability to have multiple clients in the master area of the tiled layout. This feature was dropped from vanilla dwm in version 4.4.
  - http://dwm.suckless.org/patches/historical/nmaster
