# Introduction #
As of jqMultiSelects v0.2, the second parameter to jQuery.multiSelect() is an array of options controlling the plugin's behaviour. They are described below.

For original users of v0.1 the old behaviour of the second parameter is still supported, however all parameters which were originally implicitly IDs must now be prefixed with '#' for that behaviour. More information is available at MultiSelectBackwardCompatibility.

# Details #
## trigger (selector) ##
If you want other elements to invoke the movement of the `<option>` elements, provide a selector for them here.
Defaults to none.


## autoSubmit (boolean) ##
By default, if the `<select>` has a parent `<form>` all of its child `<option>`s will be selected on that form's submit event. Without this the `<option>` values are not submitted.

To disable this behaviour, set `autoSubmit` to `false`.

Defaults to `true`.

_NOTE_: for the values to submit correctly, the `<select>` must have a valid `name` attribute ending in [.md](.md), e.g. `<select name="choices[]" ...>`


## beforeMove (function) ##
A function to be called before moving the elements. Return `true` to continue moving the elements, `false` to cancel the operation.
Defaults to none.


## afterMove (function) ##
A function to be called after moving the elements.
Defaults to none.