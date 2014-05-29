JeuxVideo.com Tools
===================

A set of tools for [JeuxVideo.com](http://www.jeuxvideo.com/).

Smileys
-------

### Description

This script will retrieve the full list of JeuxVideo.com smileys, including
a static list of hidden smileys. The list is printed to standard output.

### Dependencies

* `curl`

### Examples

I generated the static smileys list with this very command:

```sh
smileys | column -t > smileys.txt
```

Smileys Download
----------------

### Description

Download the list of smileys from JeuxVideo.com read from standard input
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
