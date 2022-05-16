# Darcula Theme from PyCharm for VS Code

[![Visual Studio Marketplace](https://vsmarketplacebadge.apphb.com/version/Bobronium.darcula-from-pycharm.svg)](https://marketplace.visualstudio.com/items?itemName=Bobronium.darcula-from-pycharm) [![Downloads](https://vsmarketplacebadge.apphb.com/downloads/Bobronium.darcula-from-pycharm.svg)](https://marketplace.visualstudio.com/items?itemName=Bobronium.darcula-from-pycharm) [![GitHub Repo stars](https://img.shields.io/github/stars/Bobronium/vscode-pycharm-darcula-theme?label=Star%20on%20GitHub&style=social)](https://github.com/Bobronium/vscode-pycharm-darcula-theme)

Fork of [Darcula PyCharm Theme](https://marketplace.visualstudio.com/items?itemName=garytyler.darcula-pycharm) with several fixes and support for semantic highlighting, including Python 3.10 Structural Pattern Matching (`match:` `case:` syntax)

* [Semantic highlighting](#enabling-semantic-highlighting)
* [Linting highlighting](#linting-highlighting)
* Optimized for [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python) + support for many popular languages
* Support for [MagicPython](https://marketplace.visualstudio.com/items?itemName=magicstack.MagicPython) RegEx highlighting (install separately)
* Jinja & Django Template support (See [Template Support](#template-support))
* Overridable base highlight (See [Customization](#syntax-customization))

## Semantic Highlighting

From [Semantic Highlighting Overview](https://github.com/microsoft/vscode/wiki/Semantic-Highlighting-Overview)
> Semantic highlighting enriches the syntax coloring based on symbol information from a language service that has the full understanding of the project.

### Enabling semantic highlighting

1. Press `⌘` `⇧` `P`
2. Search settings.json & Open
3. Paste the following

    ```js
        "editor.semanticTokenColorCustomizations.enabled": true,
    ```

[Semantic Highlight Guide](https://code.visualstudio.com/api/language-extensions/semantic-highlight-guide)

## Linting highlighting

To better match PyCharm highlighting, put this in settings.json:

```js
    "python.analysis.diagnosticSeverityOverrides": {
        "reportUndefinedVariable": "error",
        "reportImportCycles": "error",
        "reportMissingImports": "error",
        "reportMissingModuleSource": "error",
    },
    "python.linting.flake8CategorySeverity.F": "Warning",
    "python.linting.flake8CategorySeverity.E": "Information",
    "python.linting.flake8CategorySeverity.W": "Information",
    "python.linting.mypyCategorySeverity.note": "Information",
    "python.linting.mypyCategorySeverity.error": "Information",
    "python.linting.pycodestyleCategorySeverity.E": "Information",
```

Then adjust to your liking.

Colours match with PyCharm according to scheme:

| PyCharm      | VSCode      |
|--------------|-------------|
| Error        | Error       |
| Warning      | Warning     |
| Weak Warning | Information |

## Template Support

Use one of these plugins:

* [Jinja plugin](https://marketplace.visualstudio.com/items?itemName=wholroyd.jinja)
* [Better Jinja](https://marketplace.visualstudio.com/items?itemName=samuelcolvin.jinjahtml)
* [Django plugin](https://marketplace.visualstudio.com/items?itemName=batisteo.vscode-django)
* [Django Template plugin](https://marketplace.visualstudio.com/items?itemName=bibhasdn.django-html)

## Syntax Customization

To change the base text color, use a snippet like this in your `settings.json`

```js
    "editor.tokenColorCustomizations": {
        "[PyCharm Darcula Theme]": { // Targets dark GUI
            "textMateRules": [
                {
                    "name": "Foreground base syntax",
                    "scope": [
                        "text", // For markup, config, etc.
                        "source", // For code
                    ],
                    "settings": {
                        "foreground": "#FF0000" // Bright red
                    },
                },
            ]
        },
    },
```
