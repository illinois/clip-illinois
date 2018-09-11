# clip-illinois

_clip-illinois_ is a set of bash functions for OSX and linux users to manipulate clipboard contents. Tired of extracting emails from web and or email text, life too short to add/drop @illinois.edu" to convert netids to and from email addresses? clip-illinois is for you.

9am. Like a well nourished and confused cobra, the email was long and tangled, but contained a few good nuggets - I needed those email addresses and I didn't care for the surrounding text. After copying the whole text to the clipboard I *clipemails* and _Bam!_ suddenly the world was a brighter place and my clipboard a thing of beauty.

10am. "Thanks for the list of late-add students- I really need to email them..."  *add@illi* to the rescue and _Bam!_ my clipboard no longer netids but a list of email addresses.  Thanks clip-illinois.

11am. They dropped 'em faster than *drop@illi@* could remove @illinois.edu from my clipboard; now I could paste netids.  Thanks _clip-illinois_.

_clip-illinois_ was created by Lawrence Angrave who needed to do more with less time. Please send additions, chocolate and bug reports to angrave.

# Installation

````bash
#Clone this project into your home directory -
cd & git clone https://github.com/illinois/clip-illinois;

#To activate the functions inside your current bash shell-
source clip-illinois/env

#To activate clip-illinois functions when you start a new bash shell - 
echo >> ~/.bash_profile
echo "source ${home}/clip-illinois/env" >> ~/.bash_profile
````

# Features

_clip-illinois_ implements the following 3 bash functions, which you can run immediately by typing them into the terminal -

## clipemails

_clipemails_ will modify the clipboard to retain only email addresses (one per line). 
Characters and words which do not resemble an email address are discarded.
Useful when you grab html source or email and just want the embedded email addresses.


## drop@illi

_drop@illi_ will modify the clipboard to extract email addresses as netids (one per line).
Everything that is not an email address is discarded.
This is useful when you have a clipboard full of emails to be converted into netids.

## add@illi

_add@illi_ will modify the clipboard by appending "@illinois.edu" to every word that is not an email.
ie. this will convert a clipboard full of netids into emails.
Words which already contain an @ are not converted.

