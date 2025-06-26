# NAME

htag - create html in the shell

# SYNOPSIS

**htag** *tag-name* [-\-*attr-name* *attr-val*].\.. [*text-content*].\..

# DESCRIPTION

Create HTML tags and attributes in the shell.

The first argument must be the name of the tag.  All other arguments are
inserted into the tag as text content.

If the tag name is the only non-flag argument, text is read from the STDIN.

Long flags are automatically converted into attributes, and all consume one
argument as the attribute value.

Prints the created tag to the STDOUT.

# BUGS

Report bugs to <mdvorak.personal@gmail.com>.

# EXAMPLES

    $ htag p ""
    <p></p>

    $ htag p Some text
    <p>Some text</p>

    $ htag p "Some text"
    <p>Some text</p>

    $ echo "Some text" | htag p
    <p>Some text</p>

    $ htag a "An anchor tag" --href "https://foobar.baz"
    <a href="https://foobar.baz">An anchor tag</a>

    $ for FILE in $(ls)
    > do htag li "$FILE"
    > done | htag ul
    <ul><li>file1.txt</li><li>file2.txt</li><li>file3.txt</li></ul>

# SEE ALSO

Source and installation instructions at <https://temp.link.com>.
