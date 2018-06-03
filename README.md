# scheme-r7rs

Scheme language support (R7RS+/#F) for VS Code

## Features

Mostly follows R7RS syntax definitions, including the following:
- correct coloring of R7RS numerical constants, identifiers, strings, and characters
- support for `#;` comments
- support for vectors, bytevectors, quoted and backquoted forms  

Extensions:
- additional definition and syntax keywords from earlier standards and [#F](https://github.com/false-schemers/sharpF "#F - A Minimalistic Scheme System")
- support for `#&` box syntax

## Screenshots

(color theme is available as scheme-r7rs-light)

![](https://raw.githubusercontent.com/false-schemers/textmate-scheme-support/master/images/screenshot1.png)
![](https://raw.githubusercontent.com/false-schemers/textmate-scheme-support/master/images/screenshot2.png)

## Release 0.0.1

Initial release of the extension

## Known Issues

Known colorizer problems (most probably cannot be easily fixed):
- colorizer gets confused by datum prefixes such as `` ` ' , ,@ #& `` if the datum that follows is separated by newlines or comments
- definition coloring can be easily fooled by newlines and/or comments in the first two sub-forms
- `#;` comments use relaxed grammar and may be colored incorrectly in some corner cases
- coloring of backquoted expressions is not very robust; it fails if double-nested (e.g.`` `(a `(b ,,c ',,d) e)) `` or if full forms like `(unquote x)` are used. Reasonable forms from real code are colored reasonably well.
- generally, grammar is relaxed in many places, so some syntax errors won't look like errors (e.g. cons dot can be misplaced).

## Credits

Based on author's .tmLanguage extension published here: [textmate-scheme-support](https://github.com/false-schemers/textmate-scheme-support)

Flaming Lambda logo borrowed from the [Wizard Book](https://mitpress.mit.edu/sites/default/files/sicp/index.html)

