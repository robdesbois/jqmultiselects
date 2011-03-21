jQuery MultiSelects plugin v0.3
Copyright (c) 2007 Rob Desbois,
              2011 Yury Samsonov <yury.samsonov@gmail.com>

Latest version can be found at
http://code.google.com/p/jqmultiselects/

LICENCE

Dual licensed under the MIT and GPL licenses:
http://www.opensource.org/licenses/mit-license.php
http://www.gnu.org/licenses/gpl.html

Example icons from http://www.famfamfam.com/lab/icons/silk/
Licenced under Creative Commons Attribution 2.5 License
http://creativecommons.org/licenses/by/2.5/

This plugin was inspired by SelectFilter element in Django admin interface.
It adds the addition of common behaviour to <select> elements allowing multiple
options to be selected. 

ABOUT 

SelectFilter element has two panels: "source", which contains available options,
and "destination" with options selected by user.
jqMultiSelects enables you to deal purely with the presentation of your
<select> elements, and then use the plugin to attach common behaviours to them.

Current features include:
 * Set up double-click transferring of options from one select to another;
 * Enable transferring of multiple options via an external element, e.g. 
   <img>, <button>, <input>, etc.;
 * Automatic submission of <option> elements with parent form submission;
 * Callbacks to hook into the process;
 * Automatic sorting for lists.

You can use some trigger buttons to move options from source to destination
and vice versa. "Select" and "deselect" moves only selected elements,
"select all" and "deselect all" moves all elements in choosen direction.


EXAMPLE

To implement, start by creating your <select> elements:

<select name="left" id="select_left" multiple="multiple">
   <option>Item 1</option>
   <option>Item 2</option>
</select></td>

<a id="options_right" href="#">move right</a>
<a id="options_left" href="#">move left</a>

<select name="right" id="select_right" multiple="multiple">
   <option>Item 3</option>
   <option>Item 4</option>
</select>

Then, to add the Multi-Selects behaviour to these listboxes, simply call
multiSelect() function for the "source" element with "destination" as
a first argument and options as second one:

$(function() {
  var options = {
    button_select: "#options_right",
    button_deselect: "#options_left"
  };
  $("#select_left").multiSelect("#select_right", options);
});

By default all options placed to "destination" element will be sent to a
server on the form submission.


OPTIONS

All options are optional.

Trigger elements: 

 * button_select - "select" button;
 * button_select_all - "select all" button
 * button_deselect - button to remove selected options from "destination";
 * button_deselect_all - button to remove all options from "desttination".

Use jQuery selector or jq-wrapped element as a value.


Sorting options:

 * autoSort - if true, options will be sorted after moving elements (enabled
              by default);
 * sortType - "value" (default): sort by options text,
              "key": by <option>s "value" attribute,
              function(a, b) {...}: your own sorting functon as for jQuery
              sort() function.
 * sortDesc - if true, options sorted in reverse order (false by default),
              not used for you own sorting function.


Callbacks:

 * beforeMove - "before move" callback, if returns false, no items will be moved;
 * afterMove  - after move callback.

Callbacks should get three arguments: "source" list, "destination" list and
"action". Actions are: "select", "deselect" and "all".


Other options:

 * keepSelected - keep moved items selected, false by default (default value
   may or may not be changed in future versions, if it important for you do not
   relay on default value);
 * autoSubmit - select all child <option>s on parent form submission. I have
   no idea why you should want to change it, but well...



