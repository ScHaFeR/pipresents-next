PI PRESENTS  - Version 1.2.1 BETA
============================

This repository contains Beta Test software for the next version of Pi Presents. If you are unhappy with bleeding edge software then use the main Pi Presents repository and upgrade later.


FOR BETA TESTERS
================
Thank you for  helping me improve Pi Presents.

Ensure you read the Release Notes in ReleaseNotes.txt first. Improvements from Version 1.1.2 are in changelog.txt

I have made this next version of Pi Presents  a Beta as it is such a major upgrade. The main aim of the beta is to obtain feedback on the usability of the improvements and to iron out the, hopefully, few bugs left. I am also waiting for a new version of omxplayer to hit the Foundations official Raspbian release as it has seamless looping and windowing; I would like to incorporate these in the released version of Pi Presents.

To upgrade follow the instructions in the 'Updating Pi Presents' section below. Before doing so keep a copy of the original Pi Presents:

* As instructed in the instructions rename your pipresents directory to old-pipresents
* Also copy pp_home to another directory. Part of the upgrade process is to update all the profiles to Version 1.2 so these will not be useable by the current released version of Pi Presents.

PI PRESENTS
===========
Pi Presents is a display and animation control application intended for Museums and Visitor Centres. I am involved with a couple of charity organisations that are museums or have visitor centres and have wanted a cost effective way to provide audio interpretation and slide/videoshow displays. Until the Raspberry Pi arrived buying or constructing even sound players was expensive. The Pi with its combination of Linux, GPIO and a powerful GPU is ideal for black box multi-media applications; all it needs is a program to harness its power in a way that could be used by non-programmers.

This major upgrade of Pi Presents adds in all those features that I orginally envisaged and those which you kind people have suggested to me. It is now a flexible toolkit for display and animation with a large range of features. This large range of features may seem to make it complicated, hopefully not sso as most of them are optional.  I have tried to keep it simple for beginners by providing an editor with templates and a set of examples for basic applications. A extensive User Manual is also provided.

Pi Presents is basically five elements - mediashows, menus, liveshows, players for different types of track, and a GPIO output sequencer.  These can be combined using a simple to use editor to serve a great variety of simple or complex applications. Applications include:

*	Audio-visual interpretation of exhibits by triggering a sound, video, or slideshow from GPIO, keyboard or buttons.

*	A repeating media show for a visitor centre. Images, videos, audio tracks, and messages can be displayed. Different shows can be scheduled at specified times of day.

*	Allow media shows to be interrupted by the visitor and a menu of shows or tracks to be presented.

*	Showing 'Powerpoint' like presentations where progress is controlled by buttons or keyboard. The presentation may include images, text, audio tracks and videos.

*   Control animation of exhibits by switching GPIO outputs synchronised with the playing of tracks.

*   A dynamic show capability (Liveshow) in which tracks to be played can be included and deleted while the show is running.

The main framework of Pi Presents is now complete, unless of course you know better! I am startin  to look at the display of animations using OpenGLES and Pi3D, text to speech, and maybe some sort of HTML display.

There are potentially many applications of Pi Presents and your input on real world experiences would be invaluable to me, both minor tweaks to the existing functionality and major improvements.

Licence
=======

See the licence.md file. Pi Presents is Careware to help support a small museum charity of which I am a Trustee and who are busy building themselves a larger premises https://www.facebook.com/MuseumOfTechnologyTheGreatWarWw11. Particularly if you are using Pi Presents in a profit making situation a donation would be appreciated.

Installation
============

The full manual is in the file manual.pdf. To download Pi Presents including the manual and get going follow the instructions below.

Install required applications (MPlayer, PIL and X Server utils)
------------------------------------------------------

         sudo apt-get update
         sudo apt-get install python-imaging
         sudo apt-get install python-imaging-tk
         sudo apt-get install x11-xserver-utils
		 sudo apt-get install unclutter
		 sudo apt-get install mplayer

	   
Download and install pexpect
-----------------------------

Specified here http://www.noah.org/wiki/pexpect#Download_and_Installation and below.

From a terminal window open in your home directory type:

         wget http://pexpect.sourceforge.net/pexpect-2.3.tar.gz
         tar xzf pexpect-2.3.tar.gz
         cd pexpect-2.3
         sudo python ./setup.py install

Return the terminal window to the home directory.
	   
Download Pi Presents
--------------------

Pi Presents MUST be run from the LXDE desktop. From a terminal window open in your home directory type:

         wget https://github.com/KenT2/pipresents-next/tarball/master -O - | tar xz

There should now be a directory 'KenT2-pipresents-next-xxxx' in your home directory. Rename the directory to pipresents

Run Pi Presents to check the installation is successful. From a terminal window opened in the home directory type:

         python /home/pi/pipresents/pipresents.py

You will see a welcome message followed by an error message which is because you have no profiles. Exit Pi Presents using CTRL-BREAK or close the window.


Download and try an Example Profile
-----------------------------------

Warning: The download includes a 26MB video file.

Open a terminal window in your home directory and type:

         wget https://github.com/KenT2/pipresents-examples/tarball/master -O - | tar xz

There should now be a directory 'KenT2-pipresents-examples-xxxx' in your home directory. Open the directory and move the 'pp_home' directory and its contents to your home directory.

From the terminal window type:

         python /home/pi/pipresents/pipresents.py -p pp_mediashow
		 
to see a repeating multimedia show. (With this beta test you will get an error, use the editor to update  the profile to this version.)

Now read the manual to try other examples.

Reading the Manual
==================

The manual in the pipresents directory is issued as a PDF because it was too large and unwieldy to be a text file. Raspbian has a pdf reader, mupdf, however it is somewhat limited. Raspbian will soon have the better xpdf installed as default but if its not with you yet:

         sudo apt-get install xpdf
		 

Updating Pi Presents
=====================

Open a terminal window in your home directory and type:

         wget https://github.com/KenT2/pipresents-next/tarball/master -O - | tar xz

There should now be a directory 'KenT2-pipresents-next-xxxx' in your home directory

Rename the existing pipresents directory to old-pipresents

Rename the new directory to pipresents.

Copy pp_editor.cfg from the old to new directories.

You will find a few additional examples in the /pipresents/new_examples directory; copy these into /pp_home/profiles. These profiles are compatible with verson 1.2. The version 1.1 examples and any examples you have created will need updating by running them through the editor.

I have started a new thread on the forum for the beta test, see below.

		 
Requirements
============
Pi Presents was developed on Raspbian using Python 2.7. It will run on a Rev.1 or Rev.2 Pi. On 256MB machines display of large images (.jpg etc.) will run out of RAM and crash the Pi.

I don't know the exact maximum but keep images in the 1 Megapixel range. Larger images, greater than the screen pixel size, will do nothing to improve the picture and will take longer to display even on 512MB machines.

omxplayer plays some videos using 64MB of RAM; others need 128MB, especially if you want sub-titles. 


Bug Reports and Feature Requests
================================
I am keen to develop Pi Presents further and would welcome bug reports and ideas for real world additional features and uses. 

Please use the Issues tab on Github https://github.com/KenT2/pipresents-next/issues or the Pi Presents thread http://www.raspberrypi.org/phpBB3/viewtopic.php?f=38&t=29397 on the Raspberry Pi forum. ?????????
