# Command-Line-Guide

### Symbols and Uses

1. **>** redirects standard output of a command
to a file, overwriting previous content.
2. **>>** redirects standard output of a command
to a file, appending new content to old content.
3. **<** redirects standard input to a command.
4. **|** redirects standard output of a command to
another command.

### Some General keywords
1. **sort**: sorts lines of text alphabetically.
2. **uniq**: filters duplicate, adjacent lines of text.
3. **grep**: searches for a text pattern and outputs it.
4. **sed** : searches for a text pattern, modifies it and outputs it.
5. **export** VARIABLE="Value" sets and exports an environment variable.
6. **USER** is the name of the current user.
7. **PS1** is the command prompt.
8. **HOME** is the home directory. It is usually not customised.
9. **PATH** returns a colon separated list of file paths. It is customised in advanced cases.
10. **env** returns a list of environment variables.
    *e.g., env | grep PATH*
