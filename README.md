XYANK
=====

```ex
NAME
	xyank - format, build, execute, pass standard input and arguments to clipboard


SYNOPSIS
	[CMD... |] xyank X|Y [STR...]


DESCRIPTION
	modes: `x|X` for execute, `y|Y` for yank only


EXAMPLES
	# yank arguments to clipboard
	xyank Y date foo          # date foo

	# yank stdin to clipboard
	date | xyank y            # Sun Feb 25 00:00:00 AM +00 2024

	# yank stdin + arguments
	date | xyank Y foo bar    # Sun Feb 25 00:00:00 AM +00 2024 foo bar

	# execute argument & yank its stdout to clipboard
	xyank X date              # Sun Feb 25 00:00:00 AM +00 2024

	# execute stdin & yank its stdout to clipboard
	echo date | xyank X       # Sun Feb 25 00:00:00 AM +00 2024

	# execute stdin + arguments & yank its stdout to clipboard
	echo date | xyank X '+%s' # 1708796381


ENVIRONMENT VARIABLES
	XYANK_SILENT   Silent Query & Result prints


SEE ALSO
	yank(1), xsel(1), xset(1), xclipboard(1), xpaste(1)


AUTHOR
	metaory <metaory@gmail.com>, Feb 2024
```

CONFIGURATION
-------------

```ex
# to silent outputs
# export XYANK_SILENT=1

# ALIASES

alias -g YY='| xyank Y'
wc -l README.md YY      # 99 README.md

alias -g YX='| xyank X'
echo wc -l YX README.md # 99 README.md

alias yy='xyank Y'
wc -l | yy              # 99 README.md
yy wc -l README.md      # wc -l README.md

alias yx='xyank X'
yx wc -l README.md      # 99 README.md
```

Modes
-----
- `y|Y`: yank stdin, args to system clipboard
- `x|X`: execute stdin, args & yank output to system clipboard

Installation
------------

- clone repo
- give execution permissions
- place it in your path

```ex
# Clone the repo
git clone git@github.com:metaory/xyank.git

# Navigate to repo
cd xyank

# Give execution permissions
chmod +x xyank

# Link it somewhere in your PATH
ln -sfv xyank /usr/bin/xyank

# Use it anywhere

# Usage
xyank --help
```

TODO
====
- [ ] Makefile

