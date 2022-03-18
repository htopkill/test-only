<!--  This document has been written with Xwriter,  for proof of concept  -->  

# MARKDOCK

Markdock is a markup language based on markdown to create formatted text using a plain-text editor.  
This document propose new rules to use markdown for editing/sharing ' Rich-Text ' documents  

[MARKDOCK](#markdock)  
[ABOUT MARKDOCK](#about-markdock)  
[CHEAT SHEET](#cheat-sheet)  
[TABLE OF CONTENT](#table-of-content)  
[LINE BREAK/NEW LINE](#line-break-new-line)  
[HEADER](#header)  
[HEADING2](#heading2)  
[Heading3](#heading3)  
[Heading4](#heading4)  
[Heading5](#heading5)  
[Heading6](#heading6)  
[EMPHASIS](#emphasis)  
[TEXT  SIZE  AND  COLOR](#text-size-and-color)  
[LINE JUSTIFICATION](#line-justification)  
[ADVANCED TEXT JUSTIFICATION](#advanced-text-justification)  
[PAGE BREAK](#page-break)  
[HORIZONTAL  RULE](#horizontal-rule)  
[LISTS  UNORDERED](#lists-unordered)  
[LISTS  ORDERED](#lists-ordered)  
[INDENT PARAGRAPH](#indent-paragraph)  
[BLOCK  QUOTES](#block-quotes)  
[CODE  INLINE (SINGLE LINE)](#code-inline-single-line)  
[CODE  BLOCK ](#code-block)  
[LINK](#link)  
[Link HTTP](#link-http)  
[Link FILE](#link-file)  
[Link HEADER](#link-header)  
[Link MAIL](#link-mail)  
[IMAGE](#image)  
[IMAGE WITH URL / LINKS](#image-with-url-links)  
[TASK  LISTS](#task-lists)  
[TABLE ](#table)  
[TABLE HTML](#table-html)  
[ESCAPE CHARACTERS](#escape-characters)  
[DISABLE/ESCAPE HTML CODE](#disable-escape-html-code)  
[COMMENT](#comment)  
[HTML CODE](#html-code)  
[SHORTCODE](#shortcode)  
[ARCHIVE .MDZ](#archive-mdz)  
[REFERENCES](#references)  

## ABOUT MARKDOCK

Markdown has 4 main issues for editing/sharing documents :  
1. Weird rules : 2 trailing spaces for a new line, No display of extra spaces/tabs  
2. HTML code required for basic text justification/style  
3. Too many rules  for the same format  
4. No archive file containing images/objects  

**Markdock** define a new set of rules to solve these issues.  
These rules **do not break backward compatibility** but try to make smooth change  
You can always use HTML code inside a document to get full-compatibility  

Main changes introduced in **Markdock** are :  
1. No more 2 trailing spaces for new line, Extra Spaces/Tabs display  
2. Extra formatting rules for underline, paragraph ...  
3. Introduce new  'ShortCode' syntax, as {\{shortcode\}} Text {} to replace some HTML code  
4. Define a Markdow archive 7zip file '.mdz' containing  Files, Images, Objects  
5. Define clearly how to display header  

Xwriter use Markdock rules and has an option 'force NewLine' for backward compatibility  
You should use this option if Markdock rules are not used  

## CHEAT SHEET


|         MARKDOWN              |         MARKDOCK                       |  
|-------------------------------|--------------------------------------------|  
| newline: 2trailing spaces,<br\> |  No requirement for newline              |  
| Extra spaces/tabs ignored     |   Spaces/Tabs display as plain-text        |  
|   .md file                    |   .md or 7zip archive(.mdz) with objects  |  
|  \*italic\*  or  \_italic\_   |       \_italic\_                           |  
|  \*\*bold\*\* or \_\_bold\_\_ |           \*\*bold\*\*                     |  
|    \<u\>underline\</u\>         |     \_\_underline\_\_                    |  
|     \~\~strikeout~\~          |  	  \~\~strikeout\~\~                     |  
|         -                     |   \=\=highlight\=\=                        |  
|         -                     |   \+\+Big Font\+\+  (Font Size+3)          |  
| # Header 1                    |   # Header1   ( Only One, Center/Font Size+8 )|  
| ##(##) Header2-4              |   ##(##) Header2-4   (Left/Font Size+4)    |  
| #####(#) Header5-6            |   #####(#) Header5-6  (Left/Font Size+2)   |  
| Underlined headers with =/-   |   NOT SUPPORTED                            |  
| \<sup\>superscript\</sup\>      |     ^\^superscript^\^                    |  
| \<sub\>subscript\</sub\>        |     \<sub\>subscript\</sub\>             |  
| Unordered list [Spaces]- * +  |   [0-2 Tabs]- * + Unordered list           |  
| Ordered list  [Spaces]1. 1)   |   [0-2 Tabs]1. 1) Ordered list             |  
| > Block Quote                 |   > Block Quote  (begin line with >)       |  
| \<div align='center'\>        |    ::[Spaces/Tabs] Justify line center     |  
| \<div align='right'\>         |    :::[Spaces/Tabs] Justify line Right     |  
|  :[1space]Definition List     |  :[1space]Line Fully-Justify                     |  
|            -                  |   == Paragraph indentation Level1          |  
|            -                  |   === Paragraph indentation Level2         |  
|            -                  |   ==== Paragraph indentation Level3        |  
| Horizontal rule -\--/***/___  |    -\-- Horizontal Rule                    |  
|            -                         |	{{TOC}}  for Table Of Content       |  
| \<div style='page-break-after:always'\> | {{PageBreak}}  for PDF Page Break|  
| \<span style='font-family:serif;'\>   |  {\{serif}} Text Serif {}          |  
| \<span style='font-size:1.0em;'\>     |  {\{1.0em}} Text size 1.0em {}     |  
| \<span style='color:red;'\>            |  {\{#red}} Text Red  {}           |  
| \<span style='background-color:red'\> |  {\{##red}} Text background red  {}|  
|           -                          | {\{mono;#red}} Monospace red {}     |  
|    \<!--  comment  --\>               |	  \<!--  comment  --\>            |  
|   HyperLink:  [Name]\(http...)       |	 HyperLink: [Name]\(http...) or http:... |  
|   Link File:  [Name]\(FilePath)      |  Link File:  [Name]\(FilePath)      |  
|   Header Link :  [HeaderName]\(#ID)  |  Header Link: [HeaderName]\(#ID)    |  
| Image:  ![Name]\(ImagePath)          |  ![Name]\(ImagePath)                |  
|  \<img src="x" width="y" height="z"\> |  ![Name;Zoom]\(ImagePath) NEW:Zoom |  
|   \`Code Inline\`                    |   \`Code Inline\`                   |  
| Indented Code block (4spaces+Code)   | NOT SUPPORTED                       |  
|   \`\`\`[language] Code Block\`\`\`  |       \`\`\`[language] Code Block\`\`\`  |  
|   Table(Github Flavor Markdown GFM)  | Table(Github Flavor Markdown GFM)   |  
|  - [x]  Task Completed               | - [x]  Task Completed               |  
|  - [ ]  Task incomplete              | - [ ]  Task incomplete              |  
|    HTML Code. No Rules               | ONLY Inline/Block containers :  
|            -                         | Inline container: \<span xxx\> yyy \</span\>|  
|            -                         | Block container :                   |  
|            -                         | \<div xxx \>    (Start line with)   |  
|            -                         | your HTML code here...              |  
|            -                         | \</div\>        (Start line with)   |  

**IMPORTANT** :   
1. For backward compatibility only, when exporting to HTML, Xwriter authorize HTML outside Inline/Block containers but the result is not guaranteed  

## TABLE OF CONTENT

Begin line with {{TOC}} to display Table Of Content  
_Note : Xwriter do not insert the Table Of content in the file. The TOC is already available as a regular tree view on the left pane. This shortcode {{TOC}} is only use to create TOC when exporting document to HTML_   

## LINE BREAK/NEW LINE

On markdown, If you hit 'enter' between two lines (newline/linebreak), both lines are joined anyway (wrapped). For a real line break, you need to add two trailing spaces or backslash '\'  or  \<br\> at the end of the line.  

**Markdock** : you don't need two blank spaces or \<br\> : Regular 'newline/linebreak' works  

On Xwriter, for backward compatibility when you export a document, Go to Toolbar > Tool > 'Force NewLine'  ( add 2 trailing spaces at the end of each line )  


##  HEADER

Begin lines with 1 to 6 '#' follow by space  
##  HEADING2
###  Heading3
####  Heading4
#####   Heading5
######    Heading6
  
Headers are clearly defined and must respect the following rules :  
1. **Header1** :  Document Title   
The document has one and only one Header1 ( As the title of a book in a library )  
Alignment=Center.  
Font Size=Default Font Size + 8.  
Table Of Content=Level0  
2. **Header2-4** :  Chapters/Sections/Topic  
Alignment=Left.  
Font Size=Default Font Size + 4  
Table Of Content: header2/Level0,  header3/Level1,  header4/Level2  
3. **Header5-6** : Sub-Topics  
Alignment=Left.  
Font Size=Default Font Size + 2  
Table Of Content:   header5/Level3,  header6/Level4  

Colors/Borders/Uppercase/Underline/Bold...  are user-defined/set by the application.  
Underline Header with "====" / "-----" not supported  

## EMPHASIS

\_Text italic\_  _italic_  
\*\*Text Bold\*\*  **bold**  
\_\_Text Underline\_\_     __Underline__					  
\=\=Text Highlight\=\=   ==Highlight==  
\~\~Text strikeout\~\~  ~~strikeout~~  
\^\^Text superscript\^\^   ^^superscript^^  
<sub\>Text subscript</sub\>    <sub>subscript</sub>  
Combine emphasis:  ` __Mix underline **bold** now__ `  and ` **Mix bold __underline__ also** `  

## TEXT  SIZE  AND  COLOR

- **Markdock**:     ++Big font++  with    "++"  
- **Tips** : Use  superscript/subscript to display ^^small^^ font  
- For Text size/Family/color,  **Markdock** use [Shortcode Description](#shortcode)  


## LINE JUSTIFICATION

Begin line with  ':: Text ' or '::: Text ' to justify line to center/left  
:: Text **CENTER** with '::'  
::: Text **RIGHT** with ':::'  
Begin line with  ': Text ' to fully-justify the line  

: Text is fully justify. Full-justification is not available on Xwriter but will be used when exporting to HTML. This syntax is the only syntax that may break "backward" compatibility with some markdown flavor that parse ": Text" as a "Definition List". However  "Definition List" is not widely used and only with some markdown flavor. With markdock, you can easily replace definition list with "bold" and "Paragraph indent"  or try ":[tab]Definition list"  

## ADVANCED TEXT JUSTIFICATION

No **Markdock** rules for  left/center/right text justification on same line.  
Use HTML code  

- Use HTML div  block for multi-line alignment  
```  
<div style='text-align: center; white-space: pre-wrap;'>  
This is a first line  
And a second line  
</div>  
```  
- Use HTML floating element  to obtain left/center/right text on same line  
```  
<span style="float: left;"> </br> My Name </br> My Phone </span>   
<span style="float: right;">  To Mr Jhones</br> 	Phone</span>  
<div style="text-align: center;">  Dear Mr Johnes </div>  
```  
- Use HTML Table with NO border  (align = left/center/right)  
```  
<table width="100%" border="0" align="left" style="text-align: left;" >  
	<col style="width:40%">  <col style="width:45%">  <col style="width:15%">  
	<tr> <td>Debian XFCE</td>  <td></td>  <td><b>Awesome</b></td>  </tr>  
	<tr> <td>Ubuntu Gnome</td> <td></td>  <td>Not too Bad</td>  </tr>  
</table>  
```  
- For a Text Full-Justify  : Use HTML div block  
```  
<div style='text-align: justify; text-justify: inter-word; white-space: none;'>  
xxx   
</div>  
```  
## PAGE BREAK

**Markdock new rule** :  Begin line with {{PageBreak}}  
{{PageBreak}}  


## HORIZONTAL  RULE

- Begin Lines with at least 3  '---'  
----------------------------------------------------------------------  

## LISTS  UNORDERED

Begin lines with:    0 to 2  Tabs  followed with  "+" or  "-" or   "*"  
Always begin a list with 0 Tab.  Use an empty line to stop a list  
- List1. Begin nested list always with **0 TAB**  
- List1. **0 TAB**  
	- List   **1TAB**  
		- List **2 TAB**  
		- List **2 TAB**  
	- List  **1TAB**  

on Xwriter, Do **NOT** Mix Unordered/Ordered List.   Split with blank line  

## LISTS  ORDERED

Begin lines with:    0 to 2 Tabs followed with    "Number." or    "Number)"  
Always begin a list with 0 Tab.  Use an empty line to stop a list.   
1. Begin nested list always with **0 TAB**  
	1. List   **1TAB**  
		1. List **2 TAB**  
		1. List **2 TAB**  
	1. List **1 TAB**  

On Xwriter, Do **NOT** Mix Unordered/Ordered List.   Split with blank line  

## INDENT PARAGRAPH

Begin paragraph with '== '   '=\== '  or  '=\=== '   for indent level 1,2,3.  
**End each paragraph with empty line (recommended) or 3 trailing spaces**  
== Paragraph **indent 01** : This is my first line beginning with '==' and a line break now:  
This is another new line. To stop the paragraph, add 3 trailing spaces   
=== Paragraph **indent 02** :  Another test for another paragraph NEWLINE  
This paragraph end with same trailing spaces. End with 3 trailing spaces   
==== Paragraph **indent 03** :  This is the last paragraph test NEWLINE  
This indented paragraph will stop with an empty line  

Empty line above stop previous paragraph  

## BLOCK  QUOTES

Block : begin each line of a block-quote with '>'  or '>>'  
> This is a block quote  qhsdqds qjshgdjhqgsdq jqhsdjhgqh sdgqgs hdqgjsdgh hqsgdjqd qhsdgjqhgdsjhgqdqhgsdjhqdsqd  hf fqsd  qsfd gfdsdgfqsd gqsd  
>> A sub-level blockquote  
  
## CODE  INLINE (SINGLE LINE)

Use back tick for code Inline : ` echo ls | grep '\s*2' | tr -s 'g'  `   and ` puts ( echo ls) `  
Markdown formatting is disable inside  'Code inline'  

## CODE  BLOCK 

Xwriter use font monospace,  and disable all markdown formatting inside Code Block  
2 types of Code Block  :  
1. Indented Code block by indenting lines by four spaces  
Markdock **DO NOT** support this syntax. Strongly suggest to use fenced code blocks  
2. Fenced Code block with three backticks (```)  
```shell  
# This is a block code. Use font mono,disable other tags 
ls *.* | grep list | awk **notbold**  
```  
Xwriter support code highlighting : python, javascript, css, shell, tcl.  More to come  


## LINK

### Link HTTP
Syntax : [Name]\(http:...\)  
Direct Link :    https://duckduckgo.com      https://www.startpage.com  
Name Link :     [Duck Duck Go](https://duckduckgo.com)       [Start page](https://www.startpage.com)  

### Link FILE
Syntax : [Name]\(Absolute or Relative Path\)         Name can be an empty string  
Absolute Path	:  ` [My File](/etc/apt/sources.list) `  [My File](/etc/apt/sources.list)			  
Same Folder	:  ` [My File](README.md) `	[My File](README.md)					  
Sub Folder		:  ` [My File](test/QuickTest.md) `  [My File](test/QuickTest.md)  

### Link HEADER
syntax : [Description]\(#ID)  
The IDs are generated from the content of the header according to the following rules:  
- All text is converted to lowercase.  
- All spaces/non-word text (e.g., punctuation, HTML) are converted to hyphens.   
- More than 2 hypens convert to 1 hyphen  
- Trailing hyphen removed  

Example :  `[A Header Link example](#link-file)` : [A Header Link example](#link-file)  

### Link MAIL
[example@gitlab.com](mailto:example@gitlab.com)  

## IMAGE

__Format__ :  png, jpg, bmp, gif, tif, xbm, tga  
Not Supported on Xwriter : jpeg2000, webp, svg  

**Markdock new rule** :  Image display size (zoom) can be defined in Image name with ';' as separator  
- Syntax :  ![]\(Path/Image.png)  or  ![Name;Zoom]\(Path/Image.png)  
- Absolute Path: ![Name;Zoom]\(Path/Image.png)  
- Relative Path : ![Name;Zoom]\(SubFolder/Image.png or Image.png)  
- On other editors without Markdock support, the image will be display on full-size  
- Zoom Value = integer or 1/integer :   2, 3, 4, 5....  or  0.15, 0.2, 0.25, 0.3, 0.5  
- on Xwriter, same Image with different Zoom do NOT work  
Image with 0.5 Zoom  ![MyImage;0.5](test/test.jpg)  

## IMAGE WITH URL / LINKS

For security reason, Image link from the web are not downloaded automatically  :  
To display image, Go to Toolbar > Tool . Enable 'Display Web Image' and reload the document (Ctrl+r), then display image (Ctrl+r)  
Image with LINK : ![ImagewithHTTP;1](https://www.freeiconspng.com/uploads/linux-icon-19.png)  

## TASK  LISTS

- [x] this is a complete item with - \[x]  
- [ ] this is an incomplete item  with - \[ ]  
- [x] @user  

## TABLE 

Table can be display with the default text font but in **Markdock**, a table should be saved with column alignment compatible with fixed-width font by default  
1. Xwriter always use font 'monospace' for Table ( Defined in Menu > Preferences )  
2. Use spaces to align columns  
3. Justification (center/right) and some formatting (bold) not done in Xwriter but will be done when exporting in HTML  
Right now, Xwriter do not export correctly markdown table to HTML : Use Table HTML described on the next chapter if you need to export the table on HTML/PDF  

**Syntax** :  
```  
| Header1       | Header2          | Header3        |  
|---------------|:----------------:|---------------:|  
| Line1C1       |    Center Item   |     Right Item |  
| Line2C1       |     Line2C2      |        Line2C3 |  
```  
**Result** :  

| Header1       | Header2          | Header3        |  
|---------------|:----------------:|---------------:|  
| Column1       | Column2          | Column3        |  


## TABLE HTML

Include the class center in your CSS style sheet : ".center { margin-left:auto; margin-right:auto; }"  

__With Border__ :  
```  
<table class='center' width="80%"  border="1"  align="center"  style="border: 1px solid black; text-align: center;">  
	<tr>  <th>Table</th>    <th>Name</th>	    <th>Version</th>    </tr>  
	<tr>  <td>Debian</td>   <td>Jessie</td>   <td>8.0</td>        </tr>  
</table>  
```  
__With NO border__ :  
```  
<table class='center' width="100%" border="0" align="left" style="text-align: left;" >  
	<col style="width:40%">    <col style="width:45%">   <col style="width:15%">  
	<tr>   <td>Debian XFCE</td>     <td></td>    <td>Awesome</td>      </tr>  
	<tr>   <td>Ubuntu Gnome</td>    <td></td>    <td>Not too Bad</td>  </tr>  
</table>  
```  
> Note : 'NO border' can be used to justify text  
  

## ESCAPE CHARACTERS

Use backslash \\ to disable markdown format :  
 \_Not Italic\_    \*\*Not Bold\*\*  
No need to escape characters in "Code Inline" and "Code Block"  
__Supported characters__:  
	\* (asterisk)     \| (pipe)     \` (tick mark)     \_ (underscore)    \# (pound sign)  
	\+ (plus sign)    \- (minus sign/hyphen)      \^ (caret)      \=  (equal)    \< (left)   \> (right)  
    \~   \[ \]	(brackets)    \( \) (parentheses)    \\ (backslash)       \{ \}  curly braces   \: (colon)  

## DISABLE/ESCAPE HTML CODE

Use  \\<xxx\\> to disable html code  : \<span style='color:red'\> text red  \</span\>  

## COMMENT

use ` <!--   Text  -->  ` for comment :  <!--   Text  -->  


##  HTML CODE
HTML code is necessarily inside :   
- HTML inline container     \<span xxx\>  yyy  \</span\>   
Example : \<span style='color:red'\>Text\</span\> for text in red  
- HTML 'div' block container   \<div\>    xxx   \</div\>  
For 'div' block, line start with \<div\> with NO SPACE/TABS before.  
Next 'div' blocks must be indented with at least one space/tabs   
```  
<div>  
	xxx  
	<div>   
		yyy  
		<!-- Inline container can be inside 'div' block container -->  
		<span style='color:red'>Text</span>  
	</div>  
</div>  
```  

## SHORTCODE

**Markdock new rule** :  
Shortcode enables to define HTML code with 'short' alias/code:  
{{serif;1.0em;#whi;##gra;|red}} means Serif/Size1.0/Foreground white/Background gray/Border red {}  
  
Use {} to stop inline formatting: This is a {{#red}} red text {} on this line  
You can apply shortcode to multiple lines (block) : the block ends with {} or 3 trailing spaces or empty line  

**Color**  :  
Xwriter support these color code when exporting on HTML:  
		whi (white)  bla (black)  gra (gray)  sil (silver)  red (red)  blu (blue)  gre (green)  
		mar (maroon)  oli (olive)  tea (teal)  nav (navy)  ora (orange)   pur (purple)  vio (violet)  
		fuc (fuchsia) yel (yellow)  lim (lime)  aqu (aqua)  
		and any hexadecimal color (#FFAC09 for foreground, ##BBCC56 for background)  

## ARCHIVE .MDZ

**Markdock new format** :  
Markdock archive .mdz is a 7zip file container with :  
1. Only one main Markdock file with extension '.md' at the root  
2. All the images __with absolute path__ are placed in a unique sub-folder 'img'  in the archive. Absolute path are converted to a relative path as 'img/MyImage.jpg' in the Markdock file  
3. All the images with __relative path__ keep the same path: The archive recreate the directory structure to put image inside  
4. On the Markdock files, All objects path are relative and target root/sub-folders path in the archive. Relative Path Name are :  
MyImage.jpg (archive root) or Sub-Folder1/Sub-Folder2.../MyImage.jpg  
  
To generate an archive, Go to  'toolbar > Save as Archive'  
To open .mdz archive on Xwriter, Open the archive file as a normal file.  

## REFERENCES

1. [GitHub Markup Reference](https://gist.github.com/ChrisTollefson/a3af6d902a74a0afd1c2d79aadc9bb3f#file-0-github-markup-reference-readme-md)  
2.  [iOS iaWriter](https://ia.net/writer/support/general/markdown-guide)  
3.  [Markdown Guide](https://www.markdownguide.org/basic-syntax)  
4.  [Cheat_Sheet](https://www.markdownguide.org/cheat-sheet)  
5.  [Markup Comparison](https://en.wikipedia.org/wiki/Lightweight_markup_language)  
6.  [Github Flavor Markdown (GFM) Cheat sheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Here-Cheatsheet)  
7.  [GitHub Markdown Formatting](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)  
8.  [Gitlab_Advanced_Markdown](https://docs.gitlab.com/ee/user/markdown.html)  
9.  [Microsoft Markdown Reference](https://docs.microsoft.com/en-us/contribute/markdown-reference)  
