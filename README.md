# mac-wallpaper-shuffle

## Summary
Shuffle your desktop wallpaper from a directory of image files (jpg, png)

## Description
This is a bash script that leverages an macOS Automator workflow that changes the desktop wallpaper to whatever image file (jpg, heic or png) is passed in.

The script does some parameter validation, then unpacks the uuencoded Automator workflow into /tmp.  It then loops over the randomized list of files from the target (if specified) or current directory, calls the Automator workflow for the given file, then sleeps for the specified delay (or 1 hour if not specified) before repeating the process for the next image file in the list.

The script will run forever, so in the current iteration, if you background the job, you'll have to kill it to stop.

## Future Enhancements
I'd like to:
- Add automatic backgrounding
- A "stop" verb to kill a backgrounded copy of the script
- A "list" verb to show current directory being shuffled
- Ability to detect if another instance is already running
- Maybe the ability to bake the script into a launcher-level app
  
