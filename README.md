# DerStandard Terminal Liveticker

https://gir.st/dst-live.htm

## Usage

    ./ticker <dst.at-URL> [backlog-#] | ./format [img=1] [noembed=1] [wdiff=1]

Supply a `derstandard.at/jetzt/livebericht/2000xxxxxxxxx/...` url (or just the
2000xxxxxxxxx ID) to `ticker`. By default, the whole available backlog will be
immediately downloaded; you can limit backlog to any number of items by
supplying an integer as the second argument (caveat: the API will still return
all items marked as important (yellow bar in the website) on top of the number
of requested items).
Supply a truthy value for `img` to `format` to display images in-line using
Unicode half-blocks, or supply a truthy value to `noembed` to disable
inline-tweets and selected user comments. The default is to show textual
content inline, and embedded media as a URL. To enable word wise diffing of
updates, supply wdiff with a truthy value.

*Example*: `./ticker 2000103942403 0 | ./format`

Please be aware that this project is not endorsed by or affiliated with
derStandard.at and may or may not be in compliance with their terms of
service--use at your own risk.

## Requirements

 * curl
 * awk
 * fold (GNU coreutils)
 * [jq]
 * [websocat]
 * [viu] if you want inline-images
 * [wdiff] if you want diffed updates to posts

[jq]: https://github.com/stedolan/jq
[websocat]: https://github.com/vi/websocat
[viu]: https://github.com/atanunq/viu
[wdiff]: https://www.gnu.org/software/wdiff/

The `$PATH` has been adjusted within the scripts to also look in the current
directory for these uncommon binaries.

## License

Copyright (c) 2019 Tobias Girstmair (https://gir.st/)
You can study, share and improve this software under the terms of the GNU
General Public License, version 3 (see: `LICENSE`).
