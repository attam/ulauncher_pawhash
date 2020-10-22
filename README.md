# ulauncher_pawhash
Ulauncher script to generate passwords using HMAC-SHA1 algorithm (requires master password, site-specific parameter)

By default, this script generates a password and loads into the active clipboard buffer. The default password is 8 characters long and uses "default" as the master password. However, the script can be customized to meet criteria for a wide variety of common password rules:
- any length of characters
- digits required
- mixed case required
- punctuation required
- digits only
- no special characters allowed
- change default master passowrd or set custom master password in script

Requirements:
- linux-based operating system
- xclip (clipboard cli tool used to copy password into clipboard buffer)
- node

Setup:
- open Ulauncher and go to settings (gear icon on right side of input box)
- in Uluancher preferences, go to shortcuts tab and click "add shortcut"
- add keyword (eg hap)
- paste the following code into the "Query or Script" textbox:

#!/usr/bin/bash
node ~/scripts/pawhash-master/passhash2.js $@ | xclip -selection c

To run in Ulauncher, type:
hap <site parameter> <options>
  
The script is based on hashapass.com and the pawhash git repo (https://github.com/tornewuff/pawhash)
To use with Ulauncher, you will need to copy _ to the /usr/bin directory, and ensure executable permissions are set.
