# xx

`xx` is a simple text based file format for creating binary files and data buffers.

## Who Is This For?

The `xx` format was designed for those who need to describe, annotate, or simply write binary data in a text file. 

This can usually be done with either an assembler, or a tool that can parse hex dumps and transform them into a binary file. The main limitation of these tools is that you need to follow the semantics of either the assembler or the hex dump format in order to build your file the way you want.

With `xx`, there is a lot more freedom for how you can to write your data. The aim is to be an extensible, reliable format for portable binary data descriptions.

## Usage

Type hex bytes into a text file, then run:

    $ python3 xx.py file.xx

This will create a file called `file.sha256[6].bin`.

You can use the `-x` flag to do a simple hex dump to verify the contents of your buffer.

There are several example files in this repo for you to play with if you need some inspiration.

## Data Representation

The primary format for data is ASCII hex bytes. These can be represented in a number of common hex formats.

    $ cat formats.xx
    0x41, 0x41, 0x41, 0x41 -- Hex list
    $42, $42, $42, $42     -- 8 Bit
    43434343               -- Long hex string
    44 44 4444             -- Spaced out bytes (any size) 
    \x45\x45\x45\x45       -- C-style
    46h 46h 46h 46h        -- asm style
    47:47:47:47            -- MAC Address style
    "This is a string"     -- Plain old string, must use double quotes!

## Comments

Comments are a major component of .xx files. You can use a number of standard comment delimiters to take notes about bytes. 

Current list of comments:
```
--
//
#
;
%
|
All of the box drawing characters
```

## Roadmap

Version 0.2 of `xx` is the simple version that I've personally been using and testing, but I wanted more people to play with it before adding all the bells and whistles.

- [ ] Other number formats, WinDbg style: 0n11 = decimal 11, 0y11 = decimal 3.
- [ ] ANSI formatting for data
- [ ] Command and Macro interface

If you have any suggestions or ideas, feel free to submit an issue or a PR, or message me on twitter: [@netspooky](https://twitter.com/netspooky_)
