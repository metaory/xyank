XYANK
=====

```
NAME
	xyank - build, execute or pass standard input and arguments to clipboard

SYNOPSIS

	[CMD... |] xyank X|Y [STR...]

# yank arguments to clipboard
xyank Y date foo          # date foo

# yank stdin to clipboard
date | xyank y            # Sun Feb 25 00:00:00 AM +00 2024

# yank stdin + arguments
date | xyank Y foo bar    # Sun Feb 25 00:00:00 AM +00 2024 foo bar

# execute argument * yank its stdout to clipboard
xyank X date              # Sun Feb 25 00:00:00 AM +00 2024

# execute stdin & yank its stdout to clipboard
echo date | xyank X       # Sun Feb 25 00:00:00 AM +00 2024

# execute stdin + arguments & yank its stdout to clipboard
echo date | xyank X '+%s' # 1708796381
```

Modes
-----
- `y|Y`: yank stdin, args to system clipboard
- `x|X`: execute stdin, args and yank output to system clipboard

Installation
------------

- clone repo
- give execution permissions
- place it in your path

```bash
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

