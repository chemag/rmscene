# rmscene

Python library to read v6 files from reMarkable tables (software version 3).

In particular, this version introduces the ability to include text as well as drawn lines. Extracting this text is the original motivation to develop this library, but it also can read much of the other types of data in the reMarkable files.

To convert rm files to other formats, you can use [rmc](https://github.com/ricklupton/rmc), which combines this library with code for converting lines to SVG, PDF, and simple Markdown.

## Changelog

### v0.2.0

- Try to be more robust to unexpected data introduced by newer reMarkable software versions.
- Only warn once if unknown data is present, rather than for every block.
- Small API change to return type of `read_block` and `read_subblock` methods.

### v0.1.0

- Initial release


# operation

Test the parser:
``` shellsession
$ python -m src.rmscene print-blocks page_file.rm
```

Convert a .rm file into an SVG file.
``` shellsession
$ python -m src.rmscene rm2svg tests/rm/dot.stroke.rm /tmp/foo.svg
```

Convert a .rm file into an PDF file.
``` shellsession
$ python -m src.rmscene rm2pdf tests/rm/dot.stroke.rm /tmp/foo.pdf
```

## Acknowledgements

https://github.com/ddvk/reader helped a lot in figuring out the structure and meaning of the files.
