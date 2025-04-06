# Configuration
Created Freitag 28 Februar 2025

([Src](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup))

Set initial configuration.
Identitiy
---------
``$ git config --global user.name "<Name>"``
``$ git config --global user.email <Mail address>``
### Example
``$ git config --global user.name "John Doe"``
``$ git config --global user.email`` [``johndoe@example.com``](mailto:johndoe@example.com)

Editor
------
``$ git config --global core.editor <Editor name/path>``
### Example
#### Linux
``$ git config --global core.editor nano``
#### Windows
``$ git config --global core.editor "'C:/Program Files/Notepad++/notepad++.exe' -multiInst -notabbar -nosession -noPlugin"``
Change default branch name
--------------------------
By default Git will create a branch called master when you create a new repository with git init. Also VS Code expects the branch main.

``$ git config --global init.defaultBranch <Default branch name>``
### Examples
``$ git config --global init.defaultBranch main``

