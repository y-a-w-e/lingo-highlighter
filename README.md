# Lingo Syntax Highlighting for Visual Studio Code

This extension provides syntax highlighting for the Lingo scripting language in Visual Studio Code. Lingo was used for developing interactive multimedia content, such as games and simulations, using Adobe Director. This extension aims to improve the readability of Lingo code and make it easier to develop and read programs written in Lingo. It was developed during a research project that involved the examination of old net.art programs developed with Adobe Director and the programming language Lingo.

# Usage

* Open a .lng file in Visual Studio Code
* The syntax highlighting should automatically be applied


# install

Copy the folder into this directory: 

`%HOMEPATH%\.vscode\extensions\`
or
`~/.vscode/extensions/`

Should look like this:

```
└── extensions
    ├── extensions.json
    ├── lingo-highlighter
    │   ├── CHANGELOG.md
    │   ├── README.md
    │   ├── language-configuration.json
    │   ├── package.json
    │   ├── syntaxes
    │   │   └── lingo.tmLanguage.json
```

On Linux it worked by just copying the stuff to the extension directory. 
On Windows I had to add it to active extensions in the `extensions.json` file.
You can just copy this line (**Note** change your extension "path" accordingly) and add it to the end of the config before the closing `]`: 

```
{    "identifier": {      "id": "lingo",      "uuid": "000001337-1337-1337-1337-133700000000"    },    "version": "2023.2.0",    "location": {      "$mid": 1,      "path": "/c:/Users/<your-user-name>/.vscode/extensions/lingo-highlighter",      "scheme": "file"    },    "relativeLocation": "lingo-highlighter",    "metadata": {      "id": "000001337-1337-1337-1337-133700000000",      "publisherId": "",      "publisherDisplayName": "yawe",      "targetPlatform": "undefined",      "isApplicationScoped": false,      "updated": true,      "isPreReleaseVersion": false,      "installedTimestamp": 0,      "preRelease": false    }  }
```

# Add syntax highlights

You can add more highlighting by changing the `lingo.tmLanguage.json` file. 

For example you can add a keyword by adding the following under `"repository"`:
```
	"somekeyword": {
            "patterns": [
                {
                    "match": "keywordxyz",
                    "name": "keyword.control.lingo"
                }
            ]
        },
```
Don't forget to include it under `"patterns"`:
```
        {
            "include": "#somekeyword"
        }
```

The colors are defined in `"$schema": "https://raw.githubusercontent.com/martinring/tmlanguage/master/tmlanguage.json"`

More on this here <https://code.visualstudio.com/api/language-extensions/syntax-highlight-guide>

And here <https://macromates.com/manual/en/language_grammars>


