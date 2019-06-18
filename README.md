# mobilecommandhost
A script which logs any command run into a csv file. Created for use with Remote Commands on KDE-connect.

The purpose of this script is to wrap a command being called from kdeconnect's command list. This script will by default push a notification to the desktop of the user running the command, the command being run, and the results of the command. The results can optionally be spoken aloud using espeak, or sent to the remote device as a text file.

## System Requirements

A Linux-based system that can has the following installed:

- KDEConnect

- `wall`

- `espeak`

This was written for a system running Ubuntu 18.04 with the KDE Desktop, but should work as long as the proper software is installed

## Usage

./mobilecommandhost [-s | -w | -m] <Command to run>

where:

`-s` - Speaks the results of the command using espeak

`-w` - Writes the results of the command to a file and sends it to the device

`-m` - Mutes the `wall` (Write all) functionality, which pushes a notification to the desktop and all connected sessions

## File Paths

By default, the following files are stored in the following locations

__Logs__ - `${HOME}/log/mch.log` : This is a csv file of the date and time, user, command, and result of the command

__TEMP FILES__ - `/var/kdeconnect_<USERNAME>/` : This is where all of the files sent to the phone are stored before being sent.