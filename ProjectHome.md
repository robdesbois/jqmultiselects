# Introduction #
jqMultiSelects is a plugin for [jQuery](http://www.jquery.com/) which enables the addition of common behaviour to 

&lt;select&gt;

 elements allowing multiple options to be selected.

# Features #
**jqMultiSelects** enables you to deal purely with the presentation of your 

&lt;select&gt;

 elements, and then use the plugin to attach common behaviours to them.
Current features include:
  * Set up double-click transferring of options from one select to another
  * Enable transferring of multiple options via an external element, e.g. 

&lt;button&gt;

, 

&lt;input&gt;

, <a>, etc.<br>
<ul><li>Automatic submission of <br>
<br>
<option><br>
<br>
 elements with parent form submission<br>
</li><li>Callbacks to hook into the process<br>
</li><li>Size is 4.4KB or 0.6KB packed</li></ul>

<h1>Example</h1>
To implement, start by creating your <br>
<br>
<select><br>
<br>
 elements:<br>
<pre><code>&lt;select name="left" id="select_left" multiple="multiple"&gt;<br>
   &lt;option&gt;Item 1&lt;/option&gt;<br>
   &lt;option&gt;Item 2&lt;/option&gt;<br>
&lt;/select&gt;&lt;/td&gt;<br>
<br>
&lt;a id="options_right" href="#"&gt;move right&lt;/a&gt;<br>
&lt;a id="options_left" href="#"&gt;move left&lt;/a&gt;<br>
<br>
&lt;select name="right" id="select_right" multiple="multiple"&gt;<br>
   &lt;option&gt;Item 3&lt;/option&gt;<br>
   &lt;option&gt;Item 4&lt;/option&gt;<br>
&lt;/select&gt;<br>
</code></pre>

Then, to add the Multi-Selects behaviour to these listboxes, simply perform the following (usually in the <code>$(document).ready()</code> event):<br>
<pre><code>$(document).ready(function() {<br>
   $("#select_left").multiSelect("#select_right", {trigger: "#options_right"});<br>
   $("#select_right").multiSelect("#select_left", {trigger: "#options_left"});<br>
})<br>
</code></pre>

<h1>Changelog</h1>
Version 0.2<br>
<br>
<br>
<option><br>
<br>
 elements can be automatically selected upon parent form submission<br>
<b>plugin options now passed as an array<br></b> all element identifiers now taken as jQuery selectors instead<br>
<b>added beforeMove and afterMove callback functions<br>
Version 0.1<br></b> initial release<br>
<br>
<h1>Future Development</h1>
Currently planned additions (roughly in priority order) include:<br>
<ul><li>enable a graceful degradation - e.g. convert a group of checkboxes into 2 multiple selects<br>
</li><li>Add ability to manually order items within a list<br>
</li><li>Investigate <br>
<br>
<select><br>
<br>
 sorting plugins and check integration with transfers is easy</li></ul>

<h1>Discussion</h1>
I am not often on the jQuery mailing list these days, but I get notified of any activity on this project so if you have any requests, suggestions, bug reports, modifications then please post them in the 'issues' section here.