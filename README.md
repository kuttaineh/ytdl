# ytdl

_This repository is instruction, tutorial, and shortcuts._

**Written for the macOS platform; should work for GNU/Linux users as well.**

Windows instructions can be written — if someone would like to fund the work.

## Ever see something and think, ‘that won’t live long on the net.’ 

[youtube-dl](https://youtube-dl.org/) is a tool enabling you to locally store a backup copy of a video from a [wide variety](https://github.com/ytdl-org/youtube-dl/blob/master/docs/supportedsites.md) of video sharing sites, not just YouTube. 

### How do I do that?
Through youtube-dl - a public domain, meaning it is free to use and distribute, command line software tool. Command line means you’ll have to use [Terminal](https://support.apple.com/guide/terminal/welcome/mac), unless you use a GUI front-end.

## Install: 
Follow any of the install options from the [ytdl-org](https://github.com/ytdl-org/youtube-dl#installation) project page then, click back to this tutorial.

### Install keyboard shortcuts:
Open Terminal. 

Copy the following command and paste it into the Terminal window.
```
cat>>~/.zshrc
```
Press [return] 

> Note: on some computer keyboards the [return] key is labeled [enter].

Copy the following textblock and paste it into the Terminal:
```
alias y='youtube-dl --write-description'
alias l='ls -alh'
alias ..='cd ..'
alias d='cd ~/Downloads'
alias md='mkdir'
alias ...='cd $_'
```
Press [return].

The following steps require you to hold down two keyboard keys at once.

* Press, at the same time, the keyboard keys: [control] and [D]. // appends the lines (above) to the file.
* Again, press: [control] and [D]. // In this context Terminal communicates [EOT](https://en.wikipedia.org/wiki/End-of-Transmission_character), not [EOF](https://en.wikipedia.org/wiki/End-of-file) as above, thus the shell session is ended.

> Note: on some computer keyboards [control] is abbreviated [ctrl]. 
- - -
## Now let's try it!
From within the Terminal.app press, at the same time, the keyboard keys: [command] and [N]. // this opens a new Terminal window with a fresh shell session — one where the aliases defined in .zshrc are ready to go.

> “What's a shell?” In computing lingo, a shell is an interface to your computer operating system's [user space](https://techterms.com/definition/user_space). 

### Usage
Once you have youtube-dl installed and the keyboard shorcuts available:
* start by typing d[return]. // this will call up your computer account's Downloads directory (directory is synonymous with Folder).
* then, type y followed by the web address containing the video [return]. // this should allow you to download and extract the video along with producing a description file based upon the video's published description.

If you don't already have a shell interface to your computer launch Terminal in order to gain one then, type:
```
d
```
You should now see Downloads listed in your command prompt.

If nothing is happening after you type the command then remember to press the [return] key at the end of the command.  

Now try downloading a video:
```
y https://youtu.be/Li_MGFRNqOE
```
To access any of the videos you've downloaded simply launch Finder and click on your Downloads folder. Any and all of the downloaded video content will be in that folder unless you moved them or encountered an error. If you failed to type d[return] prior to typing y \<web address\>[return] then the video may be in your home directory. To check your home directory in Finder: click the Go menu and select Home.

#### Addendum: 
Sometimes a download of video from Twitter doesn't work because the default filename assigned is the full tweet — which often is too long to serve as a filename. In this situation add `--id` after the `y ` and before the url: ex. `y --id "https://twitter.com/FLSurgeonGen/status/1636707603915980803"` to name the video file after the tweet id.

For error: "Error: Unable to extract uploader id"
Apply fix found in comment containing "solved it temporarily (v2021.12.17) until there's a new update" found [here](https://stackoverflow.com/questions/75495800/error-unable-to-extract-uploader-id-youtube-discord-py).

##### Finally:
“If first you don't succeed: try, try again.”

![Command didn't work on the first try; same command issuance worked on the second attempt.](example.png)

# yt-dlp
A youtube-dl fork with additional features and fixes

See [README](https://github.com/yt-dlp/yt-dlp#readme), [INSTALLATION](https://github.com/yt-dlp/yt-dlp/wiki/Installation).

## modify y alias
If you've installed yt-dlp then you'll need to update your y alias in your shell's [runcom](https://en.wikipedia.org/wiki/RUNCOM).

### Gather info
```
echo $SHELL
```
Note the output of the command above.

#### if /bin/zsh
```
nano ~/.zshrc
```
* Scroll to the alias line which defines y.
* Change the command youtube-dl to yt-dlp
* Type: ^X, followed by Y to save and exit.
* Type:  source ~/.zshrc

#### if /bin/bash
Same as above only [edit, via] nano and source ~/.bashrc

You should now see marked performance and interface improvements. 

![Command worked on first try.](yt-dlp.png)

![Will even download from Facebook.](from_fb.png)

# Playing downloaded files

## for macOS
Recommending [IINA](https://iina.io/)

## for Windows, GNU/Linux, &c.
Recommending [VLC](https://www.videolan.org/vlc/)
