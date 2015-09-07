## sawfish-extra-menus

sawfish-extra-menus is a collection of extensions to the Sawfish
window manager which provides some extra GTK menus:

* file-browser-menu
* selection-menu
* workspace-windows-menu

### How to use them

Evaluate the following expressions on the sawfish session (or place
them in your `.sawfishrc` file and restart the window manager):

    (require 'workspace-windows-menu)
    (require 'selection-menu)
    (require 'file-browser-menu)

Then you can bind the menu functions to keys. You can do this by using
sawfish-ui (Bindings tab) or by setting the `global-keymap` variable.

Example:

    (bind-keys global-keymap
         "Super-s"    'selection-popup-menu
         "Super-w"    'workspace-windows-popup-menu
         "Super-f"    'fbm-popup-files-menu)

To configure the menus, see the description for each one.


### file-browser-menu

`file-broser-menu.jl` provides a menu to allow users manipulate files
and directories. Actions for files can be configured through the
`fbm-file-actions` variable. Actions for directories can be configured
through the `fbm-dir-actions` variable. The menu which lists files and
directories uses the ls program to get file names. The options for
`ls` can be configured through the `fbm-ls-switches` variable.

Actions for directories:

![screenshot](http://parenteses.org/mario/img/utils/sawfish-extra-menus/fbm-1.png)


Files listing:

![screenshot](http://parenteses.org/mario/img/utils/sawfish-extra-menus/fbm-2.png)


Actions for files:

![screenshot](http://parenteses.org/mario/img/utils/sawfish-extra-menus/fbm-3.png)


### selection-menu

`selection-menu.jl` provides a menu to allow users select X selections
(primary, secondary and clipboard). Actions to be applyed to
selections can be configured through the selection-actions
variable. It was inspired by Stephen Farrell's `services.jl`.

#### IMPORTANT NOTES

* Swapping selections is done by an external process. You'll need the xclip program. You can find it at [http://people.debian.org/~kims/xclip/](http://people.debian.org/~kims/xclip/).

* If pasting selections doesn't seem to work with xterms, take a look at this thread from the sawfish mailing list: [http://mail.gnome.org/archives/sawfish-list/2004-February/msg00003.html](http://mail.gnome.org/archives/sawfish-list/2004-February/msg00003.html).

![screenshot](http://parenteses.org/mario/img/utils/sawfish-extra-menus/selection-1.png)

Actions for selections:

![screenshot](http://parenteses.org/mario/img/utils/sawfish-extra-menus/selection-2.png)


### workspace-windows-menu

`workspace-windows-menu.jl` provides a menu which lists windows
per-workspace. When a window is selected from the menu, it is raised
and gets focus.

![screenshot](http://parenteses.org/mario/img/utils/sawfish-extra-menus/wwm-1.png)
