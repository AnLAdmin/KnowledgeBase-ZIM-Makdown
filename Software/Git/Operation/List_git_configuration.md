# List git configuration
Created Mittwoch 05 März 2025

Git has 3 configuration locations (scopes):

Configuration scopes
--------------------
Ordered from highest to lowest specificity.
### List of scopes

* Worktree -> [Working tree(s)](https://git-scm.com/docs/git-worktree)
	* <Git repository>/.git/config.worktree
* Local (= Git repository): 
	* <Git repository>/.git/config
* Global (= User configration)
	* Linux:
		* ~/.gitconfig
		* $XDG_CONFIG_HOME/git/config (-> only written to if it exists)
	* Windows:
		* %USERPROFILE%\.gitconfig
* System (= Global OS configuration location): 
	* Linux: 
		* /etc/gitconfig
	* Windows: 
		* %ProgramFiles%/Git/etc/gitconfig
* Portable
	* Linux: Not available
	* Windows: 
		* %ProgramData%\Git\config
		* %ALLUSERSPROFILE%\Git\config

### Applications with own git settings
Some applications have there own git settings which override the git ones:

* VS Code


All configuration
-----------------
List/show all configuration settings:
``$ git config --list``

Show configuration origin paths
-------------------------------
List/show all configuration settings with there origin file paths:
``$ git config --list --show-origin [--show-scope]``
--show-scope:	Also lists the scope names

Show scope system configuration
-------------------------------
List/show all configuration settings from scope **system**:
``$ git config --list --system [--show-origin]``

Show scope global configuration
-------------------------------
List/show all configuration settings from scope **global**:
``$ git config --list --global [--show-origin]``

Show scope local configuration
------------------------------
List/show all configuration settings from scope **local**:
``$  git config --list --local [--show-origin]``

