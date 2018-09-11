# Thanks clip-illinois!

See https://raw.githubusercontent.com/illinois/clip-illinois/master/LICENSE for license and warranty information.

_clip-illinois_ is a set of bash functions for technical-savvy OSX and linux users to manipulate clipboard contents. Tired of extracting emails from web and or email text, life too short to add/drop @illinois.edu" to convert netids to and from email addresses? _clip-illinois_ is for you.

9am. Like a well-nourished coiled cobra with a fondness for gold trinkets, the email was long and tangled, but contained a few good nuggets. I needed those email addresses and I didn't care for the surrounding text. Spending time on this snake would be crime. But after copying the whole text to my clipboard I ... *clipemails* and _Bam!_ suddenly the world was a brighter place and my clipboard a thing of beauty - Thanks _clip-illinois_.

10am. "Thanks for the list of late-add students- I really need to email them..."  *add@illi* to the rescue and _Bam!_ my clipboard no longer netids but a list of email addresses - Thanks _clip-illinois_.

11am. They dropped 'em faster than *drop@illi* could remove @illinois.edu from my clipboard; now I could paste netids - Thanks _clip-illinois_.

_clip-illinois_ was created by Lawrence Angrave who needed to do more with less time. Please send additions, chocolate and bug reports to angrave.

# Installation

````bash
#Clone this project ...
cd & git clone https://github.com/illinois/clip-illinois

#Read the source code ...
less ~/clip-illinois/env

#To activate the functions inside your current bash shell ...
source ~/clip-illinois/env

#To always activate clip-illinois functions when you start a new bash shell ...
echo >> ~/.bash_profile
echo "source ~/clip-illinois/env" >> ~/.bash_profile
````

Alternatively some users may wish to just paste the three functions directly into their bash_profile.
https://github.com/illinois/clip-illinois/blob/master/env#L59

# Features

_clip-illinois_ implements the following 3 bash functions, which you can run immediately by typing them into the terminal.

## clipemails

```bash
$ clipemails
```

_clipemails_ will modify the clipboard to retain only email addresses (one per line). 
Characters and words which do not resemble an email address are discarded.
Useful when you grab html source or email and just want the embedded email addresses.


## drop@illi

```bash
$ drop@illi
```

_drop@illi_ will modify the clipboard to extract email addresses as netids (one per line).
Everything that is not an email address is discarded.
This is useful when you have a clipboard full of emails to be converted into netids.

## add@illi

```bash
$ add@illi
```

_add@illi_ will modify the clipboard by appending "@illinois.edu" to every word that is not an email.
ie. this will convert a clipboard full of netids into emails.
Words which already contain an @ are not converted.

# FAQ
## Does this work on Windows?

No. If you create an equivalent Windows script and would like to add it to this project please email Angrave.

## Q. Where is the source code?

The script code is very short - just one file - see the script here -

https://github.com/illinois/clip-illinois/blob/master/env#L53

## Q. Does this work on Linux?

Yes _if_ you can create `pbcopy` and `pbpaste` equivalent commands to work on your Linux system. There are default versions provided but they may not work for you.

There is no single standard method to copy to or from the clipboard in Linux that works in all versions of Linux. The above commands (clipemails, add@illi drop@illi) use `pbcopy` and `pbpaste` to write to and read from the clipboard. You may need to define your own `pbcopy` and `pbpaste` scripts or aliases to copy to or paste from your clipboard. If these commands are not defined then clip-illinois/env script will automatically create aliases that use `xclip` to read/write the `X` windows clipboard -

````bash
#On OSX these lines do nothing because pbcopy and pbpaste are already available as files
type -t pbcopy || alias pbcopy='xclip -selection clipboard'
type -t pbpaste || alias pbpaste='xclip -selection clipboard -o'
````

An example of testing pbcopy and pbpaste:
````bash
$ # send output of a comand into the clipboard
$ ls | pbcopy
$ # Now you should be able to paste into a text editor and see a directory listing appear
$ # If you copy text from an email and then type
$ pbpaste
copied-text-will-be-printed-here
````
