#Multi-Node Tree Picker

`Returns: XML or CSV`

The multi-node tree picker data type allows your content editor to choose multiple nodes in the content or media trees to be saved with the current document type. This is useful for all sorts of situations such as relating a page to numerous other pages, creating a list of images/files from the media section, etc...

##Settings

There are a lot of settings for the Multi-Node tree picker, there are also some settings which determine which further settings are displayed.

###Select tree type

This setting determines if the data type will allow users to pick from either content or media. Changing this setting determines further settings in the property editor as detailed below.

![Media Picker Data Type Definition](images/MNTP-Settings-SelectTree.jpg?raw=true)

###Node selection type 
*This setting is only available when "Select tree type" setting is set to "Content".*

This setting determines if the tree picker nodes are selected by a particular parent node or by using a XPath expression. **NOTE: If using XPath only published nodes are shown.**

![Media Picker Data Type Definition](images/MNTP-Settings-NodeSelectionType.jpg?raw=true) 

###XPath Type

*This setting is only available when "Select tree type" setting is set to "Content" and "Node selection type" is set to "XPath Expression".*

This setting determines if the XPath expression is evaluated from the node being currently edited or from the root of the global tree.

When "XPath Type" is set to "Global", the expression is evaulated by using [uQuery.GetNodesByXPath](../../../../Reference/Querying/uQuery/Content/Nodes.md) This method provides some very useful tokens such as $ancestorOrSelf which allow complex expressions.

![Media Picker Data Type Definition](images/MNTP-Settings-XPathType.jpg?raw=true) 

###XPath expression
*This setting is only available when "Select tree type" setting is set to "Content" and "Node selection type" is set to "XPath Expression".*

The XPath expression should select the starting node for the editor to choose from. The expression depends on the "XPath Type" setting to determine if it is evaluated against the node being edited or the global tree.

Some common examples:

`self::*` - used with "XPath Type" being set to "From Current" - this would allow the editor to select from descendants of the node being edited

`$ancestorOrSelf/ancestor-or-self::*[@isDoc][@level=1]` - used with "XPath Type" being set to "Global" - this would allow the editor to select descendants of the homepage (assuming at level 1). See "XPath Type" setting above for more information on using tokens such as $ancestorOrSelf

![Media Picker Data Type Definition](images/MNTP-Settings-XPathExpression.jpg?raw=true) 

###Start node ID

*This setting is only available when "Select tree type" setting is set to "Content" and "Node selection type" is set to "Node Picker" or "Select tree type" is set to "Media".*

Use a content or media picker (depending on the "Node selection type" setting) to set the starting node for the editor to choose from.

![Media Picker Data Type Definition](images/MNTP-Settings-StartNodeID.jpg?raw=true) 

###Show thumbnails for media items?

*This setting is only available when "Select tree type" setting is set to "Media".*

When checked, the editor will see a thumbnail preview of the media item in the selected items.

![Media Picker Data Type Definition](images/MNTP-Settings-Thumbs.jpg?raw=true) 

###XPath filter type

The "XPath filter type" determines if the "XPath filter" expression allows the editor to select matched nodes (enabled) or  doesn't allow the editor to select matched nodes (disabled).

![Media Picker Data Type Definition](images/MNTP-Settings-XPathFilterType.jpg?raw=true) 

###XPath filter

The "XPath filter" is an XPath expression either allow or disallow (depending on "XPath filter type" setting above) the selection of matched nodes.  

![Media Picker Data Type Definition](images/MNTP-Settings-XPathFilter.jpg?raw=true) 

###Maximum node selections

Sets the maximum number of nodes the editor can select. Use -1 for unlimited.

![Media Picker Data Type Definition](images/MNTP-Settings-MaxNodes.jpg?raw=true) 

###Minimum node selections

Sets the minimum number of nodes the editor can select.

![Media Picker Data Type Definition](images/MNTP-Settings-MinNodes.jpg?raw=true) 

###Show tooltip for selected item

If checked a information icon will appear next to selected nodes, this provides further information about the node to the editor.

![Media Picker Data Type Definition](images/MNTP-Settings-Tooltip.jpg?raw=true) 

###Data as CSV or XML?

This setting determines if the data is stored as CSV data or XML.

![Media Picker Data Type Definition](images/MNTP-Settings-Tooltip.jpg?raw=true) 

###Pixel height of the tree control box

This setting determines the height of the data type when displayed to the editor.

![Media Picker Data Type Definition](images/MNTP-Settings-Height.jpg?raw=true)

##Data Type Definition Example

![Media Picker Data Type Definition](images/MNTP-DataType.jpg?raw=true)

##Content Example 

##XSLT Example

##Razor (DynamicNode) Example