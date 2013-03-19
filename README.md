# Gimmicode

## Description

Gimmicode is the contraction of "Give me Unicode". It's a small command-line utility written in ruby displaying the Unicode code point of a an entered character, as well as its name. Alternatively, it can also display the UTF-8 hexadecimal value and the Windows Alt code.

## Quick Use

    gimmicode of [-a] <character>

You may need to escape characters or surround them with quotes.

## Usage

Gimmicode ship with two commands, `of` and `convert`.

### of

`of` is the command giving the unicode code point from the entered characters.

For instance:

    gimmi@test ~ $ gimmicode of "G"
    U+0047: LATIN CAPITAL LETTER G ()

For a complete description of all the options available, you can type `gimmicode of -h`:

    -h, --help                       Show this message
    -a, --all                        Display all codes
    -w, --windows                    Display Windows alt codes
    -u, --utf8                       Display UTF-8 codes
    -d, --data DATAFILE              Check Unicode from the given file

### convert

`convert` is useful to convert the [UnicodeData](http://unicode.org/Public/UNIDATA/UnicodeData.txt) file available from Unicode.org into a readable format for the `of` command. A document describing the format is available at [http://www.unicode.org/reports/tr44/](http://www.unicode.org/reports/tr44/).

For each code point, the `convert` command retrieve the current name as well as the pre-Unicode 3.0 name and write a JSON file with those data.
This JSON file follows this convention:


     {
         "00A0": {"unicode_new_name": "NO-BREAK SPACE",
                  "unicode_old_name": "NON-BREAKING SPACE"},
         
         ...
     }

For a complete description of all the options available, you can type `gimmicode convert -h`:

    -h, --help                       Show this message
    -i, --in UNICODEDATA             Unicode.org UnicodeData file
    -o, --out UNICODEJSON            Converted JSON file

## Author

Gimmicode was made by [Frédéric Maquin](http://maquin.eu).

## License

Licensed under the terms of the WTFPL (Do What the Fuck You Want to Public License).

Please see the LICENSE included with this distribution for details.