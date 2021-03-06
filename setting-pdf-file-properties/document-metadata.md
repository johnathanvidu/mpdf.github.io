---
layout: page
title: Document Metadata
parent_title: Setting PDF file properties
permalink: /setting-pdf-file-properties/document-metadata.html
modification_time: 2015-08-05T11:59:59+00:00
---

A PDF file contains metadata about the title, author, subject, creation date, keywords. The title is usually shown
in the top of the screen when a user views the file; the rest of the metadata can be accessed by viewing Document
properties in Adobe Reader.

You can set the metadata directly using:

- <a href="{{ "/reference/mpdf-functions/settitle.html" | prepend: site.baseurl }}">SetTitle()</a>
- <a href="{{ "/reference/mpdf-functions/setauthor.html" | prepend: site.baseurl }}">SetAuthor()</a>
- <a href="{{ "/reference/mpdf-functions/setcreator.html" | prepend: site.baseurl }}">SetCreator()</a>
- <a href="{{ "/reference/mpdf-functions/setsubject.html" | prepend: site.baseurl }}">SetSubject()</a>
- <a href="{{ "/reference/mpdf-functions/setkeywords.html" | prepend: site.baseurl }}">SetKeywords()</a>

Metadata is also set automatically if you pass full HTML code to WriteHTML() including:

<ul>
<li>title is read from &lt;title&gt;...&lt;/title&gt; tags</li>
<li>subject, keywords and author are read from &lt;meta ... /&gt; tags</li>
</ul>

Whichever is set later will override previous settings.

The text should be UTF-8 encoded, but should not contain HTML mark-up tags.
<a href="{{ "/reference/mpdf-utilities/strcode2utf.html" | prepend: site.baseurl }}">strcode2utf()</a> is a useful
function provided with mPDF which converts HTML numerical entities to UTF-8 encoded string.

<div class="alert alert-info" role="alert">
  <strong>Note:</strong> Adobe Reader uses system fonts to display the
  document metadata, therefore any Unicode text can be used, even if core fonts only are being used for the
  document.
</div>

Example

{% highlight php %}
<?php

$mpdf = new \Mpdf\Mpdf();

$md = strcode2utf("&amp;#1575;&amp;#1610;&amp;#1604;&amp;#1575;&amp;#1578; &amp;#1601;&amp;#1610;&amp;#1605;&amp;#1575; &amp;#1575;&amp;#1610;&amp;#1604;&amp;#1575;&amp;#1578; &amp;#1601;&amp;#1610;&amp;#1605;&amp;#1575;");

$mpdf->SetTitle($md);

$mpdf->WriteHTML('Hello World');

$mpdf->Output();
{% endhighlight %}

# See Also

- <a href="{{ "/reference/mpdf-functions/settitle.html" | prepend: site.baseurl }}">SetTitle()</a> - Set document Title in metadata
- <a href="{{ "/reference/mpdf-functions/setauthor.html" | prepend: site.baseurl }}">SetAuthor()</a> - Set document Author in metadata
- <a href="{{ "/reference/mpdf-functions/setcreator.html" | prepend: site.baseurl }}">SetCreator()</a> - Set document Creator in metadata
- <a href="{{ "/reference/mpdf-functions/setsubject.html" | prepend: site.baseurl }}">SetSubject()</a> - Set document Subject in metadata
- <a href="{{ "/reference/mpdf-functions/setkeywords.html" | prepend: site.baseurl }}">SetKeywords()</a> - Set document Keywords in metadata
- <a href="{{ "/reference/mpdf-utilities/strcode2utf.html" | prepend: site.baseurl }}">strcode2utf()</a> - Convert HTML numerical entities to UTF-8 encoded string
