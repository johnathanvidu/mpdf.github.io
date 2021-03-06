---
layout: page
title: annotation
parent_title: HTML control tags
permalink: /reference/html-control-tags/annotation.html
modification_time: 2015-08-05T12:01:19+00:00
---

(mPDF >= 2.2)

annotation – Add an Annotation to the document

# Description

&lt;**annotation** <span class="parameter">$content</span> 
[ <span class="parameter">$pos-x</span> ] 
[ <span class="parameter">$pos-y</span> ] 
[ <span class="parameter">$icon</span> ] 
[ <span class="parameter">$author</span> ] 
[ <span class="parameter">$subject</span> ] 
[ <span class="parameter">$opacity</span> ] 
[ <span class="parameter">$color</span> ] 
[ <span class="parameter">$popup</span> ]
[ <span class="parameter">$file</span> ] /&gt;

Adds an Annotation to the document. An annotation is like a Tooltip on a webpage. The Annotation marker, like those 
of "Sticky Notes" in Adobe Reader. When the reader passes the cursor over, it will display a popup text box.

The exact position on the page can be specified using <span class="parameter">$x</span> and 
<span class="parameter">$y</span>, or left to position automatically. If <span class="parameter">$x</span> and 
<span class="parameter">$y</span> are not specified, the Annotation will be inserted at the current position of 
writing in the document. The <span class="parameter">$x</span> position (horizontal) can be overridden by the variable 
<a href="{{ "/reference/mpdf-variables/annotmargin.html" | prepend: site.baseurl }}">annotMargin</a>, which can be used 
to force the Annotation marker to display in the right margin.

The attribute <span class="parameter">$file</span> can be used to specify a file (any type) which is to be embedded 
inside the PDF document.

<div class="alert alert-info" role="alert">
    <strong>Note:</strong> All text to do with an annotation (text, author, subject) is rendered with the system font 
    and can therefore contain any Unicode character even if the document font restricts to a specific codepage.
</div>

Annotations cannot be moved or deleted by the reader.

# Parameters

<span class="parameter">$content</span>

This parameter specifies the text to appear in the popup text box.

<span class="parameter">$content</span> cannot contain any of the characters: &lt; &gt; &amp; ' *or* " and must use
the appropriate HTML entities e.g. &lt;annotation content="This is &amp;lt; 40" /&gt;

It is recommended that you use htmlspecialchars('Content', ENT_QUOTES) for this.

<span class="parameter">$pos-x</span>

Sets the <span class="parameter">$x</span> position of the (bottom left edge of the) Annotation marker, set in mm from
the left of the page.

<span class="smallblock">BLANK</span> or omitted or 0 uses the current writing position on the page, unless overridden 
by <a href="{{ "/reference/mpdf-variables/annotmargin.html" | prepend: site.baseurl }}">$annotMargin</a>.

<span class="parameter">$pos-y</span>

Sets the <span class="parameter">$y</span> position of the (bottom left edge of the) Annotation marker, set in mm 
from the top of the page. When Annotation markers are used within the text 
(<a href="{{ "/reference/mpdf-variables/annotmargin.html" | prepend: site.baseurl }}">annotMargin</a>
=<span class="smallblock">FALSE</span>), the marker is raised by the current lineheight to appear above the text.

<span class="smallblock">BLANK</span> or omitted or 0 uses the current writing position on the page.

<span class="parameter">$icon</span>

Sets the appearance of the Annotation marker.

<span class="smallblock">BLANK</span> or omitted uses <span class="smallblock">DEFAULT</span> i.e. 'Note'

**Values** (case sensitive)

- Note
- Comment
- Help
- Insert
- Key
- NewParagraph
- Paragraph

<span class="smallblock">DEFAULT:</span> Note

<div class="alert alert-info" role="alert">
    <strong>Note:</strong> The default is "Comment" when using Annotations from HTML markup &lt;span title=""&gt; 
    when <a href="{{ "/reference/mpdf-variables/title2annots.html" | prepend: site.baseurl }}">title2annots</a> 
    is <span class="smallblock">TRUE</span>
</div>

<span class="parameter">$author</span>

This specifies the name of the Author which will appear at the top of the popup text box.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span>

<span class="parameter">$subject</span>

This specifies the text to appear in the Annotation properties.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span>

<span class="parameter">$opacity</span>

Sets the opacity of the Annotation marker. Values must be greater than 0 and <= 1.

<span class="smallblock">BLANK</span> or omitted or 0: sets the opacity to the value of 
<a href="{{ "/reference/mpdf-variables/annotopacity.html" | prepend: site.baseurl }}">annotOpacity</a> 
(<span class="smallblock">DEFAULT</span> 0.5), unless 
<a href="{{ "/reference/mpdf-variables/annotmargin.html" | prepend: site.baseurl }}">annotMargin</a> forces the 
Annotations to appear in the margin, when the <span class="smallblock">DEFAULT</span> is 1

<span class="parameter">$color</span>

Specify the colour of the Annotation marker background.

**Values**

Any valid CSS color recognised by mPDF:

- #RRGGBB
- #RGB
- rgb(255,255,255)
- named colours such as white, yellow, blue etc.

<span class="smallblock">DEFAULT</span> Yellow

<span class="parameter">$popup</span>

Specify whether to show the popup box for the annotation when the PDF document is opened, and optional 
specify its dimensions and/or position.

<span class="smallblock">BLANK</span> or omitted or "0"  - the popup box is not shown.

Any other value forces the popup box to appear when the document is opened.

**Values**

&lt;nn nn&gt; - A string of 2 numbers (separated by spaces) will set the X and Y position in mm e.g. '30 30' 
will show a popup box with the top left corner 30mm from the top of the page and 30mm from the left of the page.

&lt;nn nn nn nn&gt; - A string of 4 numbers (separated by spaces) will set the X and Y position and also the
width and height in mm e.g. '30 30 80 50' will show a popup box with the top left corner 30mm from the top of the page 
and 30mm from the left of the page, a width of 80mm and a height of 50mm.

Note that the PDF Reader (e.g. Adobe Reader) may reposition the popup box as it pleases.

<span class="parameter">$file</span>

<span class="parameter">$file</span> specifies the name of a file to embed in the PDF document.

<span class="smallblock">DEFAULT</span>: <span class="smallblock">BLANK</span>

# Changelog

<table class="table"> <thead>
<tr> <th>Version</th><th>Description</th> </tr>
</thead> <tbody>
<tr>
<td>2.2</td>
<td>The function was added.</td>
</tr>
<tr>
<td>2.4</td>
<td>

Annotations cannot be moved or deleted.

(function SetUserRights removed)

</td>
</tr>
<tr>
<td>4.3</td>
<td>Attribute <span class="parameter">$popup</span> was added</td>
</tr>
<tr>
<td>5.1</td>
<td>Attribute <span class="parameter">$file</span> was added</td>
</tr>
</tbody> </table>

# Examples

## Example #1

{% highlight php %}
<?php

$mpdf = new \Mpdf\Mpdf();

$html = 'This is a paragraph about violas<annotation content="Violas are like big violins" /> about which I know very little.';

$mpdf->WriteHTML($html);

$mpdf->Output();
{% endhighlight %}

## Example #2

{% highlight php %}
<?php

$mpdf = new \Mpdf\Mpdf();

// The Annotation markers will appear 10mm in from the right margin of the page
$mpdf->annotMargin = 10;

// The Annotation markers need no transparency as they appear in the margins
$mpdf->annotOpacity = 1;

$html = 'This is a paragraph about violas<annotation content="Violas are like big violins" /> about which I know very little.';

$mpdf->Output();
{% endhighlight %}

# See Also

- <a href="http://uk3.php.net/manual/en/function.explode.php"> </a><a href="{{ "/reference/mpdf-variables/annotmargin.html" | prepend: site.baseurl }}">annotMargin</a> - Specify the x (horizontal) placement of Annotation markers
- <a href="{{ "/reference/mpdf-variables/annotopacity.html" | prepend: site.baseurl }}">annotOpacity</a> - Specifiy the default opacity used for Annotation markers
- <a href="{{ "/reference/mpdf-functions/annotation.html" | prepend: site.baseurl }}">Annotation()</a> - PHP equivalent to &lt;annotation&gt;

- <a href="{{ "/reference/mpdf-variables/title2annots.html" | prepend: site.baseurl }}">title2annots</a> - Convert all HTML element <span class="parameter">$title</span> attributes to Annotations
