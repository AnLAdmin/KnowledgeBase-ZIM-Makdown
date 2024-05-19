# Change specific alternatives
Created Mittwoch 27 März 2024

This changes the application for a specific [existing alternative](./List_all_available_alternatives.md).
# update-alternatives --config <Alternative name>

Example
-------
Change the default editor.
# update-alternatives --config editor

There are 2 choices for the alternative editor (providing /usr/bin/editor).

  Selection    Path             Priority   Status

*****

* 0            /bin/nano         40        auto mode

  1            /bin/nano         40        manual mode
  2            /usr/bin/mcedit   25        manual mode

Press <enter> to keep the current choice[*], or type selection number: <Set **number** of the option you wnat to set>
-> The star * show the active choice.

