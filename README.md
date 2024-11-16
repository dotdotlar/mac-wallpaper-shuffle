# mac-wallpaper-shuffle

## Summary
Shuffle your desktop wallpaper from a directory of image files.

## Description
This is a bash script that leverages a macOS Automator workflow that changes the desktop wallpaper to whatever image files (heic, jpeg and png) are found in the specified directory.

The script does some parameter validation, then unpacks the uuencoded Automator workflow into /tmp.  It then loops over the randomized list of image files from the current or specified target  directory, calls the Automator workflow for the given file, then sleeps for the specified delay (or 1 hour if not specified) before repeating the process for the next image file in the list.

The script now automatically backgrounds itself unless the "run once" (-1) parameter is specified.  It detects whether an existing backgrounded shuffle-wallpaper is running and kills it before backgrounding using the new parameters.

## Usage

```
usage: ./shuffle-wallpaper.bash [-1] [-d <delay>[hms]] [<image-dir>]

  Examples:
    ./shuffle-wallpaper.bash                      # current dir,   every hour
    ./shuffle-wallpaper.bash -1                   # current dir,   run once
    ./shuffle-wallpaper.bash -d 4h $HOME/Photos   # $HOME/photos   every 4 hours
    ./shuffle-wallpaper.bash -d 2h .              # current dir,   every 2 hours
    ./shuffle-wallpaper.bash -d 30m /tmp/imagedir # /tmp/imagedir, every 30 mins
    ./shuffle-wallpaper.bash -d 45s ~/Pictures    # ~/Pictures,    every 45 secs

  Default loop time is 1 hour and default time unit is hours

  Loops through all .heic, .jpg, .jpeg & .png files

```

## Future Enhancements
I'd like to:
- ~~Add automatic backgrounding~~
- ~~Ability to detect if another instance is already running~~
- A "stop" verb to kill a backgrounded copy of the script
- A "list" verb to show current directory being shuffled
- Maybe the ability to bake the script into a launcher-level app

