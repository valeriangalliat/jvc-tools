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

This script uses the `smileys` utility to retrieve the list of JeuxVideo.com
smileys and will download them all in the current directory.

The list of downloaded smileys is printed in real time to the standard output.

### Dependencies

* `smileys` (in same directory)
* `curl`
