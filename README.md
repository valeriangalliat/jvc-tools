jeuxvideo.com tools
===================

A set of tools for [jeuxvideo.com](http://www.jeuxvideo.com/).

Smileys
-------

### Description

This script will retrieve the full list of jeuxvideo.com smileys, including
a static list of hidden smileys. The list is printed to standard output.

### Dependencies

* `curl`

### Examples

I generated the static smileys list with this very command:

```sh
smileys | column -t > smileys.txt
```

Smileys download
----------------

### Description

Download the list of smileys from jeuxvideo.com read from standard input
in the current directoy.

The list of downloaded smileys is printed in real time to the standard output.

### Dependencies

* `curl`

### Examples

Using the `smileys` tool to retrieve the list and then download everything:

```sh
smileys | awk '{print $2}' | smileys-dl
```

Same thing but using the cache file if available:

```sh
[ -f smileys.txt ] && cat smileys.txt || smileys \
    | awk '{print $2}' \
    | smileys-dl
```

Video
-----

### Description

Extract a video stream URL from a [jeuxvideo.com](http://www.jeuxvideo.com/)
page containing an embeded video. This allows to play a video with
your favorite player instead of requiring Flash.

### Dependencies

* `curl`

### Examples

```sh
mpv $(video 'http://www.jeuxvideo.com/videos-editeurs/0003/00034710/grand-theft-auto-v-pc-e3-2014-un-pas-dans-la-nouvelle-generation-00121128.htm')
```

A good idea is to create a little function in your shell configuration
file, that will take a video page URL, use this tool to get the stream URL
and pass it directly to your favorite video player.

From my zsh configuration:

```sh
jvcp() {
    "$VIDEO_PLAYER" $("$DOTFILES/deps/zsh/jvc-tools/video" "$1")
}
```
