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
- bump [n] (appends ':n' to the site paramater) 

Note: I am a hobbyist programmer, and created this script to simplify my password management workflow based on my own needs. If anyone has any suggestions for improvement or has technical difficulties in making this work, I would love to hear from you, but my abilities and resources are limited. I am posting this for anyone who may be interested in modifying or using this script which I find to be quite useful to regenerate my existing passwords, or creatining new passwords on-the-fly.

Requirements:
- linux-based operating system
- xclip (https://github.com/astrand/xclip; clipboard cli tool used to copy password into clipboard buffer)
- node.js (https://nodejs.org/en/download/)
- minimist module for parsing commandline options (see: https://www.npmjs.com/package/minimist; once nodejs is installed, type: npm i minimist to install)

Setup:
- open Ulauncher and go to settings (gear icon on right side of input box)
- in Uluancher preferences, go to shortcuts tab and click "add shortcut"
- add keyword (eg hap)
- paste the following code into the "Query or Script" textbox:

#!/usr/bin/bash
node [path to passhash.js] $@ | xclip -selection c

To run in Ulauncher, type:
hap <site parameter> <options>
eg, hap google -b2mpl10 will generate a password using a master password and site password of 'default' and 'google', with the following criteria:
  - bump 2 (ie, site parameter used is 'google:2')
  - mixed case
  - punctuation
  - length: 10 characters
  
The script is based on hashapass.com and the pawhash git repo (https://github.com/tornewuff/pawhash)
