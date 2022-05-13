`awk [--options] '{}' [file]` - basic syntax
`name(parameters) {actions}` - functions syntax
`awk '/Word/ {print $0;}' file` - use like grep
`BEGIN` - run command at beginning of parsing data
`END` - run command at end of parsing data
`-F ''` - separator character
`$1 + $2` - add up column one and two
`$n` - print column `n`, if `$0` then print all columns
`{print $1"charcater"$2}` - separate output with `character`
`awk '(NR>n)'` - ignore first `n` lines
`awk 'NR==n1, NR==n2'` - work only on the range between `n1` and `n2`
`NR` - number of records (rows, lines)
`NF` - number of fields (words)
`awk '{print $1 > "file"}' file` - save output to file
`awk '{print $1}' file > file` - save output to file