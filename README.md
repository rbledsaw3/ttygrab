# ttygrab

This repo has two scripts: one for starting an ffmpeg instance that runs in the background capturing the tty display and internal mic for audio; and another for stopping this process since it's running in the background.

## Usage

To start streaming, type the following in a bash prompt:
```bash
$ ttygrab
Enter file name (including .mkv):
testing.mkv
``` 

Because this requires root privileges to grab directly from framebuffer devices (/dev/fb0), sudo will ask for your password.

To stop recording, use:
```bash
$ endstream
```
This is issue a killall command for ffmpeg, again requiring root privileges.

The video will be owned by root and write-protected. You'll need to run a chown/chmod accordingly to modify video permissions if needed.
