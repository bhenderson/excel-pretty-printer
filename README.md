# Pretty print excel files

# Installation

download the file and make it executable and put it in your path.
install the python dependencies.

Sorry this isn't easier, I basically have 0 python experience. xmldiff was just
the best xml pretty-printing lib I could find.


# Explanation:

xlsx files are actually just zip files containing many xml files. We can
unzip the file in-memory and loop over each file and pretty-print the
content.

# Git diff:

We can setup git to use this with text conversion for diffing.

    [.gitattributes]

        *.xlsx diff=excel

    [.gitconfig]

        [diff "excel"]
            textconv=excel-pretty-printer
            cachetextconv=true
            binary=true
            xfuncname = "^--- .*$"

