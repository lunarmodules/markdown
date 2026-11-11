# Changelog

## markdown 0.34

* Date: 11 Nov 2026
* Include support for Lua 5.4 and Lua 5.5 importing commits from [ldoc](https://github.com/lunarmodules/ldoc)
* Moved CI to GitHub
* Add `--version` flag to CLI: `lua markdown.lua --version`
* Add `CHANGELOG.md` to document the changes
* Add `RELEASES.md` to provide guidance to publish a new release
* Add CI workflow (`publish.yml`) to publish new releases to LuaRocks.org and GitHub Releases

## markdown 0.33

* Date: 27 Sep 2015
* ``markdown.lua`` now supports Lua 5.2 and Lua 5.3 in addition to Lua 5.1

## markdown 0.32

* Date: 31 May 2008
* Fix for links containing brackets

## markdown 0.31

* Date: 1 Mar 2008
* Fix for link definitions followed by spaces

## markdown 0.30

* Date: 25 Feb 2008
* Consistent behavior with Markdown when the same link reference is reused

## markdown 0.29

* Date: 24 Feb 2008
* Fix for `<pre>` blocks with spaces in them

## markdown 0.28

* Date: 18 Feb 2008
* Fix for link encoding

## markdown 0.27

* Date: 14 Feb 2008
* Fix for link database links with ()

## markdown 0.26

* Date: 06 Feb 2008
* Fix for nested italic and bold markers

## markdown 0.25

* Date: 24 Jan 2008
* Fix for encoding of naked <

## markdown 0.24

* Date: 21 Jan 2008
* Fix for link behavior.

## markdown 0.23

* Date: 10 Jan 2008
* Fix for a regression bug in longer expressions in italic or bold.

## markdown 0.22

* Date: 27 Dec 2007
* Fix for crash when processing blocks with a percent sign in them.

## markdown 0.21

* Date: 27 Dec 2007
*  Fix for combined strong and emphasis tags

## markdown 0.20

* Date: 13 Oct 2007
* Fix for < as well in image titles, now matches Dingus behavior

## markdown 0.19

* Date: 28 Sep 2007
* Fix for quotation marks " and ampersands & in link and image titles.

## markdown 0.18

* Date: 28 Jul 2007
* Does not crash on unmatched tags (behaves like standard markdown)

## markdown 0.17

* Date: 12 Apr 2007
* Fix for links with %20 in them.

## markdown 0.16

* Date: 12 Apr 2007
* Do not require arg global to exist.

## markdown 0.15

* Date: 28 Aug 2006
* Better handling of links with underscores in them.

## markdown 0.14

* Date: 22 Aug 2006
* Bug for *`foo()`*

## markdown 0.13

* Date: 12 Aug 2006
* Added -l option for including stylesheet inline in document.
* Fixed bug in -s flag.
* Fixed emphasis bug.

## markdown 0.12

* Date: 15 May 2006
* Fixed several bugs to comply with MarkdownTest 1.0 <http://six.pairlist.net/pipermail/markdown-discuss/2004-December/000909.html>
## markdown 0.11
* Date: 12 May 2006
* Fixed bug for escaping `*` and `_` inside code spans.
* Added license terms.
* Changed join() to table.concat().

## markdown 0.10

* Date: 3 May 2006
* Initial public release.