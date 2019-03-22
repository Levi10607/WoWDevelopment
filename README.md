# WoWDevelopment
World of Warcraft syntax highlight, auto-completion and global finder/highlighter for Sublime Text 2/3.

![](http://i.imgur.com/UyQqaab.png)

# Features:

* Full API syntax highlighting for lua, xml and toc files.
* Highlight removed/deprecated events.
* Context based autocompletion support for the whole WoW API with multi-line support.
* Global finder build system, which finds any global variables with detailed information for the current lua file.
* Global highlighter and liter tool with SublimeLinter.

# Installation:
* Download the package, unzip it then remove the *-master* suffix, and copy the folder into your Sublime Text 2/3 Packages folder. You can also install it from the Sublime Package Control.
* Open any of the supported file and set the syntax for the selected file: WoWDevelopment -> WoW Lua, WoW TOC, WoW XML.
* Recommended to delete these default Sublime Lua files to avoid conflicts:
![](https://i.imgur.com/Beyh5G4.png)
* Recommended autocompletion settings in Sublime *Preferences -> Settings* :

  "auto_complete": true,

  "auto_complete_commit_on_tab": true,

  "auto_complete_cycle": true,

  "auto_complete_selector": "meta.tag, source - comment",

  "auto_complete_with_fields": true,

# List globals with a build system in the console window with detailed information:
* In Sublime *Tools -> Build System ->* Select *Wow Global Finder*.
* *Ctrl+B* to run the system.

  # Adding globals to ignore for the build system:
  * Add a commented line in the *lua* file and list the globals with commas: -- GLOBALS: *math, string, table*

# How to highlight globals with Sublime Linter:
* First install the [SublimeLinter](https://packagecontrol.io/packages/SublimeLinter) package.
* Then add the path to *luacheck.exe* to your system PATH table, or to the *paths/windows* setting in the Sublime Linter settings:
"c:\\Users\\UserName\\AppData\\Roaming\\Sublime Text 3\\Packages\\WoWDevelopment\\WoW Global Finder\\"
* Add *"wow lua": "lua",* to the *syntax_map* in the SublimeLinter settings.
![](http://i.imgur.com/Caqp3Aj.png)
* In Sublime *Tools -> SublimeLinter -> Toggle Linter* then enable *globalfinder* and disable any other installed linters.
* Restart Sublime.

  # Adding globals to ignore for luacheck in Sublime Linter:
  * Add a commented line in the *lua* file and list the globals without commas: -- luacheck: globals *math string table*

Ignored globals:
* Global Functions: *Reference\API Reference\API Reference (blizzard).sublime-completions.txt*
* Global Booleans: *Reference\Global Reference\Global Booleans.sublime-completions.txt*
* Global Numbers: *Reference\Global Reference\Global Numbers.sublime-completions.txt*
* Global Strings: *Reference\Global Reference\Global Strings.sublime-completions.txt*

If you would like to enable autocomplete for these, just change the *.txt* extension to: *.sublime-completions*.

# Update:
Currently had I to roll back to using *.sublime-snippet* files instead of *.sublime-autocomplete* ones, since sublime currently has mutiple issues if any *autocomplete* files gets loaded for your current syntax. Hopefully it's gonna be fixed soon, and I can go back for *autocomplete* files to reduce the clutter.

Until then if you have any *.sublime-completions* file loaded for a syntax, then your buffer competions won't get shown up, and the fuzzy search for the completions brings up a lot more irrelevant hits, since it's also searing in the trigger descriptions.

*Initially forked from and based on [fRodzet](https://github.com/frodzet)'s original work, and used [Layback_](http://www.wowinterface.com/forums/member.php?u=329441)'s, [Vendethiel](https://www.wowace.com/members/vendethiel)'s and [Yuyuli](https://wow.curseforge.com/members/Yuyuli)'s help to extend it.*
