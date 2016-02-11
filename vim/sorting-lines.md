# Sorting Lines

Lines can be easily sorted in Vim with either a visual selection or a range provided in the form of `:{range}sort u`. Additional options include using:

* `sort! u` to invert your search
* `sort i` ignores case
* `sort x` to sort on first hexadecimal number in a line, ignoring leading 0x
* `sort o` to sort on the first octal number
* `sort b` to sort on the first binary number
* `sort /{pattern}/` skips the matched pattern and sorts on whatever comes afterward
