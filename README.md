# Xml2Xlsx

## Description:
Xml2Xlsx is an executable jar that enables you to create Excel XLSX files using a simple XML markup. It provides the ability for managing multiple worksheets, formatting, styling, data validation and tables.

## Usage:
```
java -jar Xml2Xlsx-[Version].jar --src [Source XML file] --tgt [Target Excel file]
```

### Example Usage:
```
java -jar xml2xlsx-1.2.2.jar --src "books.xml" --tgt "books.xlsx"
```

## Command Line Options:
Option|Description
------|-----------
--src|Used to specify the location of the input XML file.
--tgt|Used to specify the location of the output Excel file.

## XML Markup:
### Styles Markup:
XPath|Description
-----|-----------
/workbook/styles/style|Optional. Used to define re-usable styles to be applied to the cells.
/workbook/styles/style/@name|Mandatory. The name for the style. This name is used by cells to reference the style to be applied. The name can only contain numbers, letters and underscores.
/workbook/styles/style/align|Optional. Used to define the horizontal and vertical alignment for a style.
/workbook/styles/style/align/@vertical|Optional. Used to define the vertical alignment for an align property. Possible values include "top", "center" and "bottom".
/workbook/styles/style/align/@horizontal|Optional. Used to define the horizontal alignment for an align property. Possible values include "left", "center" and "right".
/workbook/styles/style/border|Optional, can have up to 4 borders defined. Used to define the border style for a cell.
/workbook/styles/style/border/@pos|Mandatory. Used to define which side of the cell the border will be applied to. Possible values include "top", "right", "bottom" and "left".
/workbook/styles/style/border/@type|Optional. Used to define the line style of the border. Possible values include "dash-dot", "dash-dot-dot", "dashed", "dotted", "double", "hair", "medium", "medium-dash-dot", "medium-dash-dot-dot", "medium-dashed", "none", "slanted-dash-dot", "thick" and "thin". If not defined the type "thin" will be applied.
/workbook/styles/style/border/@colour|Optional. Used to define the colour of the border. The colour can be defined as either an rgb colour using the format "rgb([red],[green],[blue])" (for example "rgb(125,36,210)") or using a pre-defined colour label. Possible pre-defined colour labels include "aqua", "automatic", "black", "black1", "blue", "blue1", "blue-grey", "bright-green", "bright-green1", "brown", "coral", "cornflower-blue", "dark-blue", "dark-green", "dark-red", "dark-teal", "dark-yellow", "gold", "green", "grey-25-percent", "grey-40-percent", "grey-50-percent", "grey-80-percent", "indigo", "lavender", "lemon-chiffon", "light-blue", "light-cornflower-blue", "light-green", "light-orange", "light-turquoise", "light-turquoise1", "light-yellow", "lime", "maroon", "olive-green", "orange", "orchid", "pale-blue", "pink", "pink1", "plum", "red", "red1", "rose", "royal-blue", "sea-green", "sky-blue", "tan", "tan", "turquoise", "turquoise1", "violet", "white", "white1", "yellow" and "yellow1".
/workbook/styles/style/font|Optional. Used to define the font styling of the cell.
/workbook/styles/style/font/@name|Mandatory. The name of the font style to be applied. The value should match the font names used by the operating system.
/workbook/styles/style/font/@size|Optional. An integer used to set the font size in points.
/workbook/styles/style/font/@colour|Optional. Used to define the colour of the font. The colour can be defined as either an rgb colour using the format "rgb([red],[green],[blue])" (for example "rgb(125,36,210)") or using a pre-defined colour label. Possible pre-defined colour labels include "aqua", "automatic", "black", "black1", "blue", "blue1", "blue-grey", "bright-green", "bright-green1", "brown", "coral", "cornflower-blue", "dark-blue", "dark-green", "dark-red", "dark-teal", "dark-yellow", "gold", "green", "grey-25-percent", "grey-40-percent", "grey-50-percent", "grey-80-percent", "indigo", "lavender", "lemon-chiffon", "light-blue", "light-cornflower-blue", "light-green", "light-orange", "light-turquoise", "light-turquoise1", "light-yellow", "lime", "maroon", "olive-green", "orange", "orchid", "pale-blue", "pink", "pink1", "plum", "red", "red1", "rose", "royal-blue", "sea-green", "sky-blue", "tan", "tan", "turquoise", "turquoise1", "violet", "white", "white1", "yellow" and "yellow1".
/workbook/styles/style/font/italic|Optional. An empty element used as a flag to indicate if the font should have italic styling applied.
/workbook/styles/style/font/strikeout|Optional. An empty element used as a flag to indicate if the font should have the strikeout styling applied.
/workbook/styles/style/wrap|Optional. An empty element used as a flag to indicate text wrapping should be applied to the cell. If a cell contains newline characters represented as "\n" then this flag must be included for the newlines to be properly displayed.
/workbook/styles/style/format|Optional. Used to define the data type and pattern format applied to the cell.
/workbook/styles/style/format/@type|Mandatory. Used to specify the data type. Possible values include "formula", "string", "int", "float" and "date".
/workbook/styles/style/format/@pattern|Optional. If @type is specified as a "date" then this attribute can be used to define the date pattern (e.g. "dd/MM/yyyy").
/workbook/styles/style/fill|Optional. Used to define the fill style for a cell.
/workbook/styles/style/fill/@colour|Mandatory. Used to define the colour of the fill. The colour can be defined as either an rgb colour using the format "rgb([red],[green],[blue])" (for example "rgb(125,36,210)") or using a pre-defined colour label. Possible pre-defined colour labels include "aqua", "automatic", "black", "black1", "blue", "blue1", "blue-grey", "bright-green", "bright-green1", "brown", "coral", "cornflower-blue", "dark-blue", "dark-green", "dark-red", "dark-teal", "dark-yellow", "gold", "green", "grey-25-percent", "grey-40-percent", "grey-50-percent", "grey-80-percent", "indigo", "lavender", "lemon-chiffon", "light-blue", "light-cornflower-blue", "light-green", "light-orange", "light-turquoise", "light-turquoise1", "light-yellow", "lime", "maroon", "olive-green", "orange", "orchid", "pale-blue", "pink", "pink1", "plum", "red", "red1", "rose", "royal-blue", "sea-green", "sky-blue", "tan", "tan", "turquoise", "turquoise1", "violet", "white", "white1", "yellow" and "yellow1".
/workbook/styles/style/fill/@pattern|Optional. Used to define the fill pattern of the cell. Possible values include "alt-bars", "big-spots", "bricks", "diamonds", "fine-dots", "least-dots", "less-dots", "no-fill", "solid-foreground", "sparse-dots", "squares", "thick-backward-diag", "thick-forward-diag", "thick-horz-bands", "thick-vert-bands", "thin-backward-diag", "thin-forward-diag", "thin-horz-bands" and "thin-vert-bands".

### Data Validations Markup:
XPath|Description
-----|-----------
/workbook/validations/validation|Optional. Used to define re-usable data validation rules to be applied to cells.
/workbook/validations/validation/@name|Mandatory. The name for the data validation. This name is used by cells to reference the data validation to be applied. The name can only contain numbers, letters and underscores.
/workbook/validations/validation/type|Mandatory. The type of data validation to be applied. Possible values include "fixed-list" and "formula-list".
/workbook/validations/validation/values|Mandatory if type is set to "fixed-list".
/workbook/validations/validation/values/value|Mandatory. One or more values to be used in the data validation.
/workbook/validations/validation/formula|Mandatory if type is set to "formula-list". Can be specified using Excel style reference formulas, including other tabs. For example "'Books'!$B$2:$B$5".

### Worksheet Markup:
XPath|Description
-----|-----------
/workbook/worksheet|Mandatory. Used to specify a worksheet tab to be included in the Excel file.
/workbook/worksheet/@name|Mandatory. The name of the worksheet tab.
/workbook/worksheet/@autofilter|Optional. Used to define if auto filters should be applied to the first row in the worksheet. This option is ignored if a table has been defined for the worksheet as auto filters are automatically applied to tables.
/workbook/worksheet/table|Optional. Used to define if the worksheet data should be contained within a table.
/workbook/worksheet/table/@name|Mandatory. The name for the table. The name can only contain numbers, letters and underscores.
/workbook/worksheet/table/@colStripes|Optional. Used to specify if column colour striping should be applied. Possible values include "true" and "false".
/workbook/worksheet/table/@rowStripes|Optional. Used to specify if row colour striping should be applied. Possible values include "true" and "false".
/workbook/worksheet/table/@style|Optional. Used to define the style type of the table. Possible values include "TableStyleDark1", "TableStyleDark2", "TableStyleDark3", "TableStyleDark4", "TableStyleDark5", "TableStyleDark6", "TableStyleDark7", "TableStyleDark8", "TableStyleDark9", "TableStyleDark10", "TableStyleLight1", "TableStyleLight2", "TableStyleLight3", "TableStyleLight4", "TableStyleLight5", "TableStyleLight6", "TableStyleLight7", "TableStyleLight8", "TableStyleLight9", "TableStyleLight10", "TableStyleLight11", "TableStyleLight12", "TableStyleLight13", "TableStyleLight14", "TableStyleLight15", "TableStyleLight16", "TableStyleLight17", "TableStyleLight18", "TableStyleLight19", "TableStyleLight20", "TableStyleDark21", "TableStyleMedium1", "TableStyleMedium2", "TableStyleMedium3", "TableStyleMedium4", "TableStyleMedium5", "TableStyleMedium6", "TableStyleMedium7", "TableStyleMedium8", "TableStyleMedium9", "TableStyleMedium10", "TableStyleMedium11", "TableStyleMedium12", "TableStyleMedium13", "TableStyleMedium14", "TableStyleMedium15", "TableStyleMedium16", "TableStyleMedium17", "TableStyleMedium18", "TableStyleMedium19", "TableStyleMedium20", "TableStyleMedium21", "TableStyleMedium22", "TableStyleMedium23", "TableStyleMedium24", "TableStyleMedium25", "TableStyleMedium26", "TableStyleMedium27" and "TableStyleMedium28".
/workbook/worksheet/row|Mandatory. Used to specify a row of data to be added to the Excel file. Maximum number of rows that can be included is 1,048,576.
/workbook/worksheet/row/cell|Mandatory. Used to specify a cell of data to be added to the Excel file. Maximum number of cells or columns that can be included is 16,384.
/workbook/worksheet/row/cell/@style|Optional. The name of the re-usable style to be applied to the cell.
/workbook/worksheet/row/cell/@validation|Optional. The name of the re-usable validation to be applied to the cell.


## Examples:
### A Simple Table With Auto Filters:
Picture|XML
-----|-----------
foo|```
<workbook>
	<worksheet name="Books" autofilter="true">
			<row>
				<cell>Title</cell>
				<cell>Author</cell>
				<cell>Year</cell>
				<cell>Price</cell>
			</row>
			<row>
				<cell>Everyday Italian</cell>
				<cell>Giada De Laurentiis</cell>
				<cell>2005</cell>
				<cell>30.00</cell>
			</row>
			<row>
				<cell>Harry Potter</cell>
				<cell>J K. Rowling</cell>
				<cell>2005</cell>
				<cell>29.99</cell>
			</row>
			<row>
				<cell>XQuery Kick Start</cell>
				<cell>Vaidyanathan Nagarajan</cell>
				<cell>2003</cell>
				<cell>49.99</cell>
			</row>
			<row>
				<cell>Learning XML</cell>
				<cell>Erik T. Ray</cell>
				<cell>2003</cell>
				<cell>39.95</cell>
			</row>
	</worksheet>
</workbook>
```
bar|```
<workbook>
	<worksheet name="Books" autofilter="true">
			<row>
				<cell>Title</cell>
				<cell>Author</cell>
				<cell>Year</cell>
				<cell>Price</cell>
			</row>
			<row>
				<cell>Everyday Italian</cell>
				<cell>Giada De Laurentiis</cell>
				<cell>2005</cell>
				<cell>30.00</cell>
			</row>
			<row>
				<cell>Harry Potter</cell>
				<cell>J K. Rowling</cell>
				<cell>2005</cell>
				<cell>29.99</cell>
			</row>
			<row>
				<cell>XQuery Kick Start</cell>
				<cell>Vaidyanathan Nagarajan</cell>
				<cell>2003</cell>
				<cell>49.99</cell>
			</row>
			<row>
				<cell>Learning XML</cell>
				<cell>Erik T. Ray</cell>
				<cell>2003</cell>
				<cell>39.95</cell>
			</row>
	</worksheet>
</workbook>
```