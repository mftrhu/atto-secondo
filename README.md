# atto-secondo

> A simple, single-page, single-file CYOA creator

## Usage

To try it out, simply go to <https://mftrhu.github.io/atto-secondo/atto_secondo.html>, or download and open the `atto_secondo.html` file offline in a JS-enabled browser - it is completely self-contained.

A mostly empty page, containing three textareas, will be shown.  The largest textarea, marked "Markdown source", will hold the source of the story (Markdown can be used for the formatting).  The two other libraries allow the creation of custom JS and CSS code for the story.

## Story syntax

The story can be written in Markdown format (the subset supported by [marked.js][marked.js]), using the [Mold][mold] syntax for templating and to display any variables, with some slight differences.

A line beginning and ending with `=` (e.g. `=START=`) denotes the start of a new section, or page.  The `=HEADER=` section is special, and will always be shown in the `header` section.

A section can be linked to by using a normal markdown link to a local fragment - e.g. `[Go back](#enemy_introduction)`.  The destination should be the name of the section linked to, slugified by turning it to lower case, removing any non-word characters, and replacing runs of spaces with a single underscore character (`_`).

If no section has been defined yet, that source is in the **prelude**.  Metadata can be specified in the prelude by using the `key: value` syntax.

Some of that metadata is special:

 - `title`: specifies the title of the story;
 - `description`: specifies the description of the story (Markdown can be used here), which will be shown before the story starts;
 - `hide_prelude`: if set, title and description of the story will not be displayed before its start;
 - `first_page`: allows a different section than the first one defined to be used as the start of the story.

## Libraries used

atto-secondo relies on [marked.js][marked.js] (MIT) and [mold][mold] (Zlib) for the bulk of its functionality (Markdown rendering and templating), and on [Blob.js][Blob.js] (MIT) and [FileSaver.js][FileSaver.js] (MIT) to allow saving of the created story.

[marked.js]: https://github.com/markedjs/marked
[mold]: https://github.com/marijnh/mold
[Blob.js]: https://github.com/eligrey/Blob.js/
[FileSaver.js]: https://github.com/eligrey/FileSaver.js/
