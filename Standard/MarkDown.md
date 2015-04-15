MarkDown 介绍
===================================
* [1. 概述](#概述)
* [2. 块级元素](#blockElement)
	* [2.1 标题](#header)
	* [2.2 换行](#lineBreak)
	* [2.3 段落](#paragraph)
	* [2.4 引用](#quote)
	* [2.5 列表](#list)
	* [2.6 代码块](#codeBlock)
	* [2.7 分割线](#horizontalRule)
* [3. 行内元素](#spanElement)
	* [3.1 强调](#emphasis)
	* [3.2 链接](#link)
		* [3.2.1 自动链接](#autoLink)
		* [3.2.2 行内链接(inline)](#inlineLink)
		* [3.2.3 引用链接(reference)](#referenceLink)
	* [3.3 图片](#image)
* [4. 转义符号 \"\\\"](#backSlash)
* [5. 表](#table)
   
* * *
   
<h2 id="overview">1. 概述</h2>
Markdown 是一种轻量级的标记语言，它是专门针对编写web文档而设计的一种书写格式，在语法上力争做到易读、易写、易编辑。  
Markdown并不是要替代HTML语法，甚至跟HTML语法没有相似性，它的语法集很小，只是相应HTML tag的一个很小的子集。  
从某种意义上说，HTML是一种发布格式（publishing format），Markdown是一种书写格式（writing format）。  
   
* * *
   
<h2 id="blockElement">2. 块级元素</h2>
<h3 id="header">2.1 标题</h3>
标题有两种语法形式。  
使用独占一行的一个或者多个=和-，可以将其上一行声明为一级标题和二级标题。  
Markdown:

	This is a first level header.
	==
	This is a second level header.
	--
  
Output:

This is a first level header.
==
This is a second level header.
--

在句首使用一到六个#可以声明一到六级标题。   
Markdown:

	# This is a first level header.
	## This is a second level header.
	### This is a third level header.
	#### This is a fourth level header.
	##### This is a fifth level header.
	###### This is a sixth level header.
    
当然，在句尾可以使用#来结束此行，这并不是必须的，甚至数量也是无所谓的。  
**注意：#后不能包含空格，否则#将会被当作标题的一部分**。    
Markdown:

	# This is a first level header. ###
	## This is a second level header. ###
	### This is a third level header.###
	#### This is a fourth level header.###
	##### This is a fifth level header.#########
	###### This is a sixth level header. #
  
Output:

# This is a first level header. ###
## This is a second level header. ###
### This is a third level header.###
#### This is a fourth level header.###
##### This is a fifth level header.#########
###### This is a sixth level header.#

<h3 id="lineBreak">2.2 换行</h3>
换行需要在当前行结尾输入不少于两个空格，然后回车换行。不然，`<br>`是不会插入的。  

<h3 id="paragraph">2.3 段落</h3>
Markdown使用一个或者多个空行来标记段落。空行指的是不包含任何任何内容或者只包含空格，tab等的行。   
Markdown:

	Now is the time for all good men to come to the aid of their country. This is just a regular paragraph.

	The quick brown fox jumped over the lazy dog's back.


Output:

Now is the time for all good men to come to the aid of their country. This is just a regular paragraph.

The quick brown fox jumped over the lazy dog's back.


<h3 id="quote">2.4 引用</h3>
Markdown使用>来表示引用。并且引用可以嵌套，只需要多加几个>即可。   
Markdown:

	> This is the first level.
	>> This is the second level.
	>>> This is the third level.
	>>
	>>  back to second level
	>
	> back to the first level

Output:

> This is the first level.
>> This is the second level.
>>> This is the third level.
>>
>>  back to second level
>
> back to the first level

Markdown很智能，你不需要在每一行都添加>，只要在某段(用*空行区分*段)文本的第一行加一个">"，则这一段内容，都会直接被引用。      
Markdown:

	> Now is the time for all good men to come to the aid of their country. 
	This is just a regular paragraph.

	>> The quick brown fox jumped over the lazy dog's back.

Output:

> Now is the time for all good men to come to the aid of their country. 
This is just a regular paragraph.

>> The quick brown fox jumped over the lazy dog's back.

<h3 id="list">2.5 列表</h3>
列表分为有序列表和无序列表。  
无序列表使用 '*' '+' 或者 '-' 来表示。    
Markdown:

	* 第一项
	* 第二项
	* 第三项

	> + 第一项
	> + 第二项
	> + 第三项

	- 第一项
	- 第二项
	- 第三项

Output:

* 第一项
* 第二项
* 第三项

> + 第一项
> + 第二项
> + 第三项

- 第一项
- 第二项
- 第三项

有序列表直接使用数字加'.'来表示。数字甚至不需要按照顺序来排列，markdown会自动将序号赋值为从一开始的顺序数字。  

Markdown:
	
	1. 第一项
	2. 第二项
	3. 第三项

	
	5. 第一项
	7. 第二项
	1. 第三项

Output:


5. 第一项
7. 第二项
1. 第三项

<h3 id="codeBlock">2.6 代码块</h3>
代码块是用来标识程序或者源代码的。在Markdown中，标识代码块是很容易的，**以空行开头**，把代码块的每一行**缩进**4个空格或者一个tab即可。  
代码块会在遇到**不缩进**的行或者到文档最后才结束。   
在代码块中，&（ampersand）和<>(angle bracket)会被自动转义为HTML实体。因此在引入HTML代码片段时候就很方便了，拷贝黏贴后，缩进每一行，Markdown将处理所有转换的麻烦。  
**注意：** 在代码块中，所有的符号都是字面意思，不会被转义为Markdown的语法，例如文档中的标记为Markdown的例子，都是使用了代码块来直接书写的。   

Markdown: 

	<div class="footer">
        &copy; 2004 Foo Corporation
    </div>

Markdown:

	* 第一项
	* 第二项
	* 第三项

在行内，可以使用反引号（` back quote）来标记一段代码。    
Markdown:

	Get help from `man bash`

Output:

Get help from `man bash`

<h3 id="horizontalRule">2.7 分割线</h3>
不少于三个的连词符(- hyphen)，星号(* asterisk)，下划线(_ underscore)单独占一行，那么就会生成水平分割线。    
如果你愿意，可以在这些符号中间添加任何的空格。

Markdown:

	***
	* * *
	********************************************
	---
	- - -
	------------------------------------
	___
	__  __
	____________________________________

Output:

***

* * *

* *   *

********************************************

---

------------------------------------

___

__  __

____________________________________


     
<h2 id="spanElement">3. 行内元素</h2>
<h3 id="emphasis">3.1 强调</h3>
强调分为两种，斜体和粗体。使用一个*或者_，可以将内容标记斜体，使用两个符号则可以标记粗体。  
**注意**：*或者_都必须紧贴着需要强调的内容，如果有空格，将无法起到强调作用。  

Markdown:

	*Italic*    _Italic_

	**Strong**	__Strong__

	This is * normal *    _  normal _

Output:

*Italic*    _Italic_

**Strong**	__Strong__

This is * normal *    _  normal _

<h3 id="link">3.2 链接</h3>
<h4 id="autoLink">3.2.1 自动链接</h4>
使用尖括号括起URL，可以设定一个简单的链接。  
概括为`<URL>`

Markdown:

	<http://cn.bing.com>

Output:

<http://cn.bing.com>


<h4 id="inlineLink">3.2.2 行内链接(inline)</h4>
方括号(square bracket)括起链接的文本，紧跟着的圆括号(parenthese)括起对应的URL，在URL之后，可以跟一个用双引号(quote)括起来的*可选的*title。   

可以概括为`[text](URL ["title"])`

Markdown:
	
	[This is bing home](http://cn.bing.com "bing")

Output:

[This is bing home](http://cn.bing.com "bing")

如果链接到本地的页面，可以使用相对地址。

Markdown:
	
	Go to [About me](/aboutme/) to find something help.

Output:

Go to [About me](/aboutme/) to find something help.

<h4 id="referenceLink">3.2.3 引用链接(reference)</h4>
在第一个方括号之后，再跟一个方括号，其中指定引用的ID。而引用的ID可以在本文档中的其他任何位置出现。  
ID可以为字母，数字，空格和标点符号等。如果想更简单一点，那么你可以将ID设置为空，而将引用中的ID设置的跟Text一样。  

可以概括为`[Text][ID]`  `[ID]: URl`   

Markdown:

	This is [an example][1] reference link.
	This is [another example][2] reference link.
	This is [third example][] reference link.

	[1]: http://example.com
	[2]: http://anotherExample.com
	[third example]: http://thirdExample.com

Output:

This is [an example][1] reference link.   
This is [another example][2] reference link.   
This is [third example][] reference link.   

[1]: http://example.com "example"
[2]: http://anotherExample.com "another example"
[third example]: http://thirdExample.com


<h3 id="image">3.3 图片</h3>
了解了链接后，图片就很简单了，只是在连接的模式前面添加了一个感叹号(exclamation )。   
可以概括为：`![Alt text](http://link.to.image "title")`

Markdown:

	![bing iamge](http://s.cn.bing.net/az/hprichbg/rb/BentsSask_ZH-CN12561671211_1920x1080.jpg "bing home")

Output:

![bing iamge](http://s.cn.bing.net/az/hprichbg/rb/BentsSask_ZH-CN12561671211_1920x1080.jpg "bing home")
   
当然，图片也是支持引用的，规则跟link一样。    

* * *

<h2 id="backSlash">4. 转义符号"\"</h2>
在有意义的词前面添加转义符(backslash)，就消除了它的Markdown语法。
Markdown:

	We dont make it \*strong*\.
	
Output:

We dont make it \*strong*\.
   
* * *

<h2 id="table">5. 表</h2>
 



 * * *
 
* [1. 概述](#概述)
* [2. 块级元素](#blockElement)
	* [2.1 标题](#header)
	* [2.2 换行](#lineBreak)
	* [2.3 段落](#paragraph)
	* [2.4 引用](#quote)
	* [2.5 列表](#list)
	* [2.6 代码块](#codeBlock)
	* [2.7 分割线](#horizontalRule)
* [3. 行内元素](#spanElement)
	* [3.1 强调](#emphasis)
	* [3.2 链接](#link)
		* [3.2.1 自动链接](#autoLink)
		* [3.2.2 行内链接(inline)](#inlineLink)
		* [3.2.3 引用链接(reference)](#referenceLink)
	* [3.3 图片](#image)
* [4. 转义符号 \"\\\"](#backSlash)
* [5. 表](#table)

