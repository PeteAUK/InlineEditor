Class: InlineEditor {#InlineEditor}
===================================
Edit-in-Place Control

InlineEditor Method: constructor {#InlineEditor:constructor}
-------------------------------------------------------------

### Syntax:
	var e = new InlineEditor(element, options);

### Arguments:

1. element - (*mixed*) an element or element id
2. options - (*object*) InlineEditor options

### Options:
* url			- (*string, optional*) url to send the save request to
* data			- (*object, optional*) extra data to send along with the save request.
* data_id		- (*string, optional*) Sohrthand method to pass in {data:{id:'xxx' }} on the object
* empty_msg		- (*string, optional*) the message to show when the element is empty. You can use html.
* hide_buttons	- (*bool, optional*) hides the 'save' and 'cancel' buttons, use ENTER to submit, ESC to cancel.
* format		- (*string, optional*) A format code of the type Nx where x is the number of decimal places to format with. Only use this if the data type is numerical.
* method		- (*string, optional*) Http method used to send the data. Can be GET, POST or JSONPOST. Defaults to 'GET';

### Events:

* onSuccess	- called after the edit is complete, argument is the new text

### Example:
	new InlineEditor(element, {url: 'save-change.php', 'id':15});
	
You can also place these attributes on the element its self, like this:
	
	<div class='editable' data-url='save-change.php'>data value</div>
	
	<!-- 
	since sending a row_id along with the data is so common, you can include it as 
	an attribute to be send as extra data. This is equivilent to using 'data: {id: 2}'
	-->
	<div class='editable' data-url='save-change.php' data-id='2'>data value</div>

	// then you could initialize all these at once like this:
	$$('.editable').each(function(item) { new InlineEditor(item); }
	