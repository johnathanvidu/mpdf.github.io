---
layout: page
title: AliasNbPages()
parent_title: mPDF functions
permalink: /reference/mpdf-functions/aliasnbpages.html
modification_time: 2015-08-05T12:00:40+00:00
---

(mPDF >= 1.0)

AliasNbPages – Defines the placeholder used to insert total number of pages into the document

# Description

void **AliasNbPages** ( string <span class="parameter">$text</span> )

Set the value for the variable string <a href="{{ "/reference/mpdf-variables/aliasnbpg.html" | prepend: site.baseurl }}">aliasNbPg</a> which is used as a placeholder used to insert total number of pages into the document.

# Parameters

<span class="parameter">$text</span>

Defines the text for the vaiable <span class="parameter">$aliasNbPg</span>.

<span class="smallblock">DEFAULT</span>: {nb}

# Examples

Example #1

{% highlight php %}
<?php

$mpdf = new \Mpdf\Mpdf();

$mpdf->AliasNbPages('[pagetotal]');

$mpdf->WriteHTML('
There are [pagetotal] pages in this document
');

$mpdf->Output();

?>
{% endhighlight %}

Example #2

{% highlight php %}
<?php

$mpdf->AliasNbPages('[pagetotal]');

is the exact equivalent of:

$mpdf->aliasNbPg = '[pagetotal]';
{% endhighlight %}

# See Also

<ul>
<li class="manual_boxlist"><a href="{{ "/what-else-can-i-do/replaceable-aliases.html" | prepend: site.baseurl }}">Replaceable Aliases</a></li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-functions/aliasnbpagegroups.html" | prepend: site.baseurl }}">AliasNbPageGroups()</a> - Sets the placeholder alias for the total number of pages in a document or page group</li>
</ul>
