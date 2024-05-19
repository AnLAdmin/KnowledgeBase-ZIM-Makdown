# Convert to git
Created Samstag 13 Januar 2024

If you work with text, you need version control. That rule applies regardless of whether you write code or poetry (some might argue that those two are the same, anyway). Ignoring the CVS and SVN dinosaurs two distributed version control systems are being regarded as state of the art: Git and Mercurial. Functionality-wise they are nearly identical, but it seems that Git, with its open-source background, is poised to take over the enterprise, too, where Mercurial used to be strongest.
For Starters

If you are just getting started with version control, take a look at the excellent SourceTree client software, and consider one of the popular hosting services Bitbucket, Github or Visual Studio Online, each of which have very usable free plans (although it should be mentioned that Github offers private repositories only for paid accounts).
Conversion

If have have been using version control for some time you might have a number of Mercurial repositories that you want to convert to Git. The remainder of this article explains how to do that on Windows.

This guide assumes you have TortoiseHg and Git installed. When installing Git make sure to select the option Use Git from the Windows Command Prompt as shown in the following screenshot. No other software is required.

2015-06-01 01_40_42-Git Setup
Preparation
-----------

Edit your mercurial configuration file (located in %Userprofile%\mercurial.ini), adding the following lines:

```ini
[extensions]
hggit = 
hgext.bookmarks =

[git]
intree = True
```


This enables the hg-git extension and instructs it to create .git repository directories next to .hg repository directories instead of putting them in subdirectories named git.

On the command line, make sure hg-git is enabled correctly by running:

$ hg help hggit

It should print something like this:

hggit extension - push and pull from a Git server

This extension lets you communicate (push and pull) with a Git server. This
way you can use Git hosting for your project or collaborate with a project
that is in Git.  A bridger of worlds, this plugin be.

Try hg clone git:// or hg clone git+ssh://

For more information and instructions, see "hg help git"

list of commands:

 gclear        clear out the Git cached data
 gexport       export commits from Mercurial to Git
 gimport       import commits from Git to Mercurial
 git-cleanup   clean up Git commit map after history editing
 gverify       verify that a Mercurial rev matches the corresponding Git rev

(use "hg help -v hggit" to show built-in aliases and global options)

Converting a Mercurial Repository to Git
----------------------------------------

On the command line, navigate to the mercurial repository you want to convert. This is the directory that contains the .hg subdirectory.

Run the following command to make a bookmark of master for default, so a reference gets created:

$ hg bookmark -r default master

Run the following command to create the .git repository directory:

$ hg gexport --debug

### Starting Over

If you made a mistake or forgot something and want to start over simply delete the .git subdirectory and run:

$ hg gclear

Git: Turning a Bare into a Working Repository
---------------------------------------------

You now have a bare Git repository in addition to the existing Mercurial repository. Turn the bare into a working repository by running:

$ git config --bool core.bare false

Create the index (otherwise, Git believes everything has been deleted, since a bare .git repository doesn’t include a file index):

$ git reset HEAD -- .

Your local source directory now contains both a Mercurial and a Git repository:

