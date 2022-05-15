# Changelog

## 0.1.2

- Fix highlighting for decorator symbol (`@`)

## 0.1.1

- Fix highlighting for `__magicmethods__`
- Fix highlighting for builtin prperties like `__name__` or `__class__`

## 0.1.0

- Fix python highlighting in embeded blocks of code (e.g. markdown code blocks)

Semantic highlighting!
- Partially fix self, cls variables highlighting
  ```py
  def f(self):  # self is highlighted here
      self.i = 1  # and here
  self = 'var'  # but not here
  ```
  Pycharm highlights first parameter of any method
  This theme will highlight only self and cls parameters of any function or method regardless of their position.
  Unfortunatyly, VSCode doesn't really understand how these parameters work.

- Fix higlighting in annotations
  ```py
  from typing import Any
  a: type["Any"] = int  # type is highlighted, Any is highlighted as class
  ```
- Fix module __variables__ highlighting
  ```py
  if __name__ == '__main__':  # __name__ is not highlighted
      print('yay')
  ```
- Fix highlighting of reassigned builtins
    ```py
    type('')  # type is highlighted here
    type = 'variable'  # but not here
    print(type)  # and not here
    ```

See changelog for original theme on GitHub: [vscode-darcula-pycharm-theme/CHANGELOG.md](https://github.com/garytyler/vscode-darcula-pycharm-theme/blob/8ac67ce56a2c19856c3e80872e2bc51c65ba5b92/CHANGELOG.md)
