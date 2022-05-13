## General

- Put a number before most commands and it will execute them multiple times. For example `20p` pastes the buffer 20 times.

## Close / Exit

`ZZ` - :wq!
`ZQ` - :q!

## Moving around

### Text

`f + character` - move at next "character"
`F + charcater` - move at previous "character"
`t + character` - move to next "character"
`T + charcater` - move to previous "character"
`gj` - move down a visual line if the line visually takes up more than one line
`gk` - move up a visual line if the line visually takes up more than one line
`J`  - join lines together and add space
`gJ` - join lines without adding a space (equivalent of `:join!`)
`<` - indent in modifier
`>` - indent out modifier
`g<` - indent in modifier and keep selection
`g>` - indent out modifier and keep selection
`=` - format modifier

### Document

`gg` - beginning of document
`G` - end of document
`<C-d` - move down half a screen
`<C-u` - move up half a screen
`zz` - places line in the middle the page
`H` - place cursor at the beginning of the screen
`M` - place cursor at the middle of the screen
`L` - place cursor at the end of the screen

## Deleting & changing

`D`  - delete to end of line
`C`  - delete to end of line and go in -INSERT-
`dd` - delete line
`cc` - clear line and go in -INSERT-
`ciw` - delete word go in -INSERT-
`diw` - delete word regardles of where you are
`dt[letter]` - delete to letter

## Selecting & copying & pasting

`v` - select characters
`V` - select lines
`vap` - select current paragraph
`vi + character` - select string between chracters: `()`, `[]`, \`\`, `<>`, `{}`
`va + character` - select string between (and including) chracters: `()`, `[]`, \`\`, `<>`, `{}`
`<C-V>` - enter visual block, allows selecting columns of text
`<C-V> + o` - move the other corner of --VISUAL BLOCK--
`yy` - yank/copy whole line
`yip` - yank in paragraph
`<C-r>=` - expression register, enter thing to get calculated and it will insert the result, `:h float-functions` and `:h float-list` for all functions you can use in it
`:put =` - expression register on new line

## Commands

`:%s/old/new/g` - replace text (string-old -> string-new) everywhere
`/string` - go to "string" forward in text
`?string` - go to "string" backwards in text
`.` - repeat previous sequence
`:earlier 1m` - go back to the state the file was 1 minute ago
`:later 1m` - go to the state the file was 1 minute ahead
`:read !command` - paste the output of a terminal command
`:read !ls` - paste all the files in a directory
`g??` - rot13 encode current line
`q:` - view command history

## Buffers, Windows, Tabs, Splits

`:bn` - buffer next
`:bp` - buffer previous
`<C-w>s` - horizontal split
`<C-w>v` - vertical split
`:sp file` - split window horizontally and open `file`
`:vsp file` - split window vertically and open `file`
`:only` - close all windows except the current one

## Substitute

`:%s/oldText/newText` - basic substitution
`g&` - rerun last substitution on all lines

## Sauces

http://www2.geog.ucl.ac.uk/~plewis/teaching/unix/vimtutor
https://vimcasts.org

## Before using

1. Rebind CAPS to ESC:
	- On Windows:
		* Install MS PowerToys
		* Keyboard Manager
		* Replace CAPS with ESC
2. Speed up key repeat:
	- On Windows:
		* Keyboard properties
		* Repeat delay: short
		* Repeat rate: fast

## General Tips

- Use words instead of remembering characters
  * `ci(` - change in parenthesis
  * `di(` - delete in parenthesis
  * `ci"` - change in next quotes on line
- Make a box with CTRL+V and r, use . too
- `:%s/\s\+$//e` remove leading whitespace
	* The colon enters command mode
	* The s is short for the substitute command
	* The percent sign specifies that the entire file should be affected (not just the current line).
	* the first two forward slashes delimit the search pattern
	* \s stands for a whitespace character, and the escaped plus sign (+) indicates that one or more spaces should be matched, preceding a line end (the dollar sign)
	* the last two slashes delimit the replacement string. Here, it is blank, so it replaces trailing whitespace with nothing.
	* The e flag suppresses an error message if no matches are found.
- `:g/^$/d` remove empty lines
- `dd:[number]put` move current line to a specific line
- `map <leader>p yi":!command <C-r>" & disown<CR><CR>` Open files in quotes in file, if they're in the same directory

## Books in vim

`ggg?G` - select whole file and encrypt so you don't get spoiled, do again to decrypt