# Simple PHP CSS Parser

Simple PHP CSS Parser: A Parser to read and alter css contents using PHP or Codeigniter

It is a very simple CSS parser based on PHP, its read CSS file as well as CSS string and make a parsed PHP array.

This class comes with all the functions necessary to make searching, alteration, addition and removal of any thing inside css file or string easily and putting it back everything as a complete css codes to css file dynamically or exporting as a string back to program.

This class is ready to use in your PHP based project as well as Codeigniter v2 or v3 framework. Just initialize the class in PHP core project or load as library into Codeigniter framework.

# Installation

## Core PHP 
  1) require('Cssparser.php');
  
  2) $css = new Cssparser();
  
## Codeigniter
  1) put the Cssparser.php file into application/libraries folder of codeigniter.
  
  2) Inside any controller, load it as a normal library
     $this->load->library('cssparser');
     
  3) $this->cssparser->read_from_file($folder."/css/custom.css");
  
# Methods
* `read_from_file` : Read css file and build PHP Array `$css->read_from_file('myfolder/myfile.css');`
 
* `read_from_string` : Read css using string and build PHP Array `$css->read_from_string('html{font-family:sans-serif;-ms-text-size-adjust:100%;-webkit-text-size-adjust:100%}');`
 
* `find_parent` : Find a CSS using css rule selector E.g `$css->find('#wrapper');` or `$css->find('.wrapper');`

* `find_parent_by_property` : Find a css rule using css property E.g `$css->find_parent_by_property('background-color');`

* `find_parent_by_value` : Find a css rule using css property value E.g `$css->find_parent_by_value('350px');`

* `find_property_value_pair` : Find a css rule using css property value pair E.g `$css->find_property_value_pair('background-color','#FFF');`

* `add_parent` : Add a new css rule with its css property and value E.g `$css->add_parent('#bodywrapper', array('background-color'=>'#FFF'));`

* `remove_parent` : Remove any css rule E.g `$css->remove_parent('#bodywrapper');`

* `rename_parent` : Rename any css rule E.g `$css->rename_parent('#bodywrapper');`

* `add_property` : Add new css property into css rule E.g `$css->add_property('#bodywrapper', 'max-width', '100px', true);` Passing `true` in the 4th parameter will all class to create new parent css rule if already not exsist into the current parsed css array, passing `false` will return false if parent not found into the PHP Array.
 
* `update_property` : Update already exsisted css property inside any css rule  E.g `$css->update_property('#bodywrapper', 'max-width', '600px');`

* `remove_property` : Remove already exsisted css property from any css rule E.g `$css->remove_property('#bodywrapper', 'max-width');`

* `export_css` : Export css rule as a string, this will incude all of the changes you have done till now on css `$css->export_css();`

* `save` : Save the entire css codes into the same css file passed on `read_from_file` function E.g `$css->save();`
