autoStorage
===========
##A jQuery plugin for automatic webstorage
[www.phunkei.de](http://www.phunkei.de/)

**REQUIREMENTS**

You need jQuery to run this plugin. I used jQuery v1.6.4 to develope this plugin, but older versions may handle it too. Your browser needs support for webstorage stuff.


**HOWTO**

Just call autoStorage() on any set of forms (e.g. $('form').autoStorage();) and the values will be saved in the specified webstorage by submitting the form and reloaded by reloading the page.


**IMPORTANT**

*	Every form needs a unique name.

*	Every element in the form needs a unique name (except radiobuttons).

*	For element names containing array-brackets, use indeces. (e.g name[1], name[2] ... multipe fields with the same name will cause overwriting data)


**SETTINGS / PARAMETERS**

*	**"storageType" : "local" | "session"**

	Define the type of storage. At the moment there is no support for sqlite (As it is absolutely useless due a lack of support by most browsers).
	The default is **"local"**. If you are new to the webstorage feature: "localStorage" keeps the data like forever while "sessionStorage" is a temporary storage, that will be deleted after you quit your browser.
	
*	**"exclude" : ["element1", "element2" ... ]**

	Pass an array with element names to exclude from storage.
	
*	**"submit" : true | false**

	Defines wether the form will be submitted. Set this to **false**, for ajax like forms.

	
**EXAMPLE**

```javascript
$(document).ready( function() {
	
	$('form').autoStorage( {
		'submit' : true,
		'storageType' : 'local',
		'exclude' : ['textfield1', 'textfield2']
	});
	
});
```

**LICENSE**

Copyright 2014 Daniel Miguel Baltes Amado

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.