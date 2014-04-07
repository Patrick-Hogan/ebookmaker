ebookmaker
==========

ebookmaker is a Python3 script that takes a JSON book description
and a bunch of HTML files, and builds an eBook.
The script generates the boring part of the eBook metadata, e.g.
the index that appears both in contents.opf, toc.ncx, and
in a HTML page.

To allow the script to generate the various tables of contents
(content.opf, toc.ncx, and the HTML index; although this last one
may be hand made, if you want) the HTML content must follow a couple
 of simple rules:

* Use header tags consistently: `<h1>` for section/chapter,
  `<h2>` for subsection, `<h3>` for subsubsection.
* Use the `"id"` attribute to identify the entry in the index.

Examples
--------

In the future I'll document the JSON book description format,
for now there are a couple of books in the examples directory.
Enter the examples directory and run the script like this to
build ePub files:

    $ python3 ../../ebookmaker BOOK.json

Recipes
-------

The 'recipes' directory is also interesting, there you'll find
Python scripts that download content not available in ebook format,
but as HTML, format it and calls on ebookmaker to assembly in a
nice ebook.

Usage
-----

    ebookmaker [-h] [-o OUTPUT] ebookData

positional arguments:

    ebookData             JSON file containing the ebook information.

optional arguments:

    -h, --help            show this help message and exit
    -o OUTPUT,            Name of the output file.
    --output OUTPUT
