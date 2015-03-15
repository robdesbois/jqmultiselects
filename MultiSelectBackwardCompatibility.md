# Introduction #
The original version of **jqMultiSelects** did not use jQuery selectors throughout, but instead some parameters had to be element IDs.

Since v0.2 this behaviour has changed: all parameters identifying elements must now be jQuery selectors.

Some of the original behaviour is still available, but some is now broken by this improvement. This is detailed below.


# Details #
**jqMultiSelects** v0.1 used the following syntax:
`$("#my_select_left").multiSelect("my_select_right", "my_move_right_button");`

As of **jqMultiSelects** v0.2, this is no longer valid syntax.

The minimum change required to make this compatible with v0.2 is simply to make the destination `<select>` identifier a selector instead (note the addition of `#` to the first parameter:
`$("#my_select_left").multiSelect("#my_select_right", "my_move_right_button");`

To access the new features offered by v0.2, the required syntax is:
`$("#my_select_left").multiSelect("#my_select_right", {trigger: "#my_move_right_button"});`
Additional options may then be added to the associative array as required.