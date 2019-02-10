# a3dsk2woz
This is a modification of the original command-line tool dsk2woz by Tom Harte, that converts Apple II DSK images to WOZ format.
This version adds the volume numbers and track syncronisation needed to pass the SOS copy protection checks.

Usage:

    a3dsk2woz input.dsk output.woz

Reads the contents of the disk `input.dsk` and outputs the WOZ-format file `output.woz`.

## Building
There are no dependencies beyond the C standard library. So e.g.

    cc a3dsk2woz.c -o a3dsk2woz

## DOS 3.3 versus Pro-DOS
Apple II DSK images contain implicitly-ordered sectors; the order depends on whether the image contains a DOS 3.3 image or a Pro-DOS image.

For the purposes of this tool if the file extension of the input disk has a 'p' in it then it is treated as a Pro-DOS image. Otherwise it is treated as a DOS 3.3 image.
