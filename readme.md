# The January 1901 issue of _The Antiquary_

## An experiment in Github-based proofreading

The files in this repository are page scans I've made of a 1901 issue of _The Antiquary_ magazine, and accompanying transcriptions of the text on each page. 

The _initial_ transcription was machine-generated OCR code, filtered and cleaned up slightly by some scripts I'm working on. As you know, OCR algorithms are only about 99% accurate---on a per-character level, tested on 12-point laser-printed Times Roman on modern bright white paper. Old books and magazines can be read quite well sometimes, but every material artifact has its own quirks that interfere more or less with that accuracy: unusual typefaces, unexpected typesetting conventions, complex page layouts, marginalia, foxing, library stamps, &c &c

The goal therefore is to **fix the text**.

## Starting point

For the purposes of the experiment, only cursory visual checks of the OCR text were made. Whole blocks may have been skipped by the algorithm, or undesirable text added (I've seen this most often where stray marks, tears, foxing or complex illustrations are "recognized" by the software).

The magazine issue is 32 pages long. There are 32 low-resolution image files in `img/screen`, and the corresponding markdown transcriptions are in `txt/`.

As convenience scripts arise, they'll appear in `lib/`.

## End point(s) and goals

I'd like to end up with a number of things:

1. a clean, correct HTML edition of the whole
2. the ability to render HTML or other formats---because Markdown
3. a suite of convenient scripts that can support this sort of effort on participants' own local systems, rather than a centralized "work hub"
4. a "style sheet" consisting of some semantic markup and some reasonable guidelines, suitable for working on more issues of the same magazine---or old books more generally
5. a self-contained system for making the book into a _server_ of its own content

## What to do

If you'd like to participate:

- fork this repository into your own Github account
- clone your forked copy to your local computer
- make sure you have the [ruby `kramdown` gem](https://github.com/gettalong/kramdown) installed on your system; it's the basis of the rendering system I'll be using
- find one or more things to improve in the markdown files
- submit a pull request!

### Guidelines

- Try to leave the line endings more or less the way they appear in the original text, except
  - *close up hyphenated words*: the initial scripts I've run have made most of these into "optional hyphen" ¬ characters, which _may not all_ need to be removed. There's no way to thoughtfully close up `Numer¬ous` but not `will-nilly`, for example.
  - *check hyphens, en- and em-dashes*: the scripts have also replaced OCR's en- and em-dashes with kramdown's character strings, but as with everything else they may not have been recognized correctly. An en-dash is represented with two hyphens (`--`), and an em-dash three (`---`).
  - *close up punctuation*: Some older printers set extra whitespace around quotes, semicolons and colons. And of course the OCR is inherently dumb. Even if the original page has extra space, modernize the spacing around punctuation marks---including em-dashes.
  - *semantic markup trumps visual*: If this particular magazine uses small caps for the intial word of an article, it should be marked up not as "small caps", but as some sort of "initial word" style.
  - ask questions and open issues!
- 

## What's doesn't work

There's no support yet for

- rendering the markdown into a single stitched-together HTML file
- high-resolution illustrations

## License

The original page images and text are in the Public Domain.

### Regarding scripts

Consider everything to be under an MIT License:

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.