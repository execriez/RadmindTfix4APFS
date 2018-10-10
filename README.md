# RadmindTfix4APFS
Prepare Radmind transcripts for MacOS APFS filesytems

## Description:

RadmindTfix4APFS removes resource forks from a filesystem and re-uploads affected Radmind transcripts.

Deploying a transcript that contain resource forks to an APFS filesystem will throw errors - since APFS filesystems do not support resource forks.

The script also removes SIP protected files from transcripts (using RadmindTfix4SIP).

## How to use:

NOTE: This script makes changes to the active filesystem by removing resource forks.

First, find a test workstation with an HFS filesystem and a MacOS prior to MacOS 10.13. 

Next, deploy transcripts from your Radmind server to this Mac OS workstation in the usual way.

Now, in a shell type:
	
	RadmindTfix4APFS
	
The script will ask if you want a dummy run, answer Y or N.

If it is not a dummy run, the script will ask for the address of your Radmind server.

(NOTE: You may want to change the 'lcreate' line within the script to match your particular upload options.)

The script will work through the active transcripts (as defined by command.K), it will remove SIP protected files from the transcript, and it will remove any resource files referenced in the transcript from the active filesystem. The script will then re-upload the affected transcripts to your Radmind server.

When the script finishes, you should Update and Check-in these transcripts at your server. Checksums will differ so transcripts need updating.

These transcripts will then be deployable to an APFS filesystems (hopefully).


## History:

1.0.2 - 10 OCT 2018

* Previous version included a broken RadmindTfix4SIP. This is now fixed. 

1.0.1 - 08 AUG 2018

* First release.
