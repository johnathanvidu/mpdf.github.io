---
layout: page
title: tabSpaces
parent_title: mPDF Variables
permalink: /reference/mpdf-variables/tabspaces.html
modification_time: 2015-08-05T12:02:32+00:00
---

(mPDF >= 2.3)

# Description

int **tabSpaces**

Specifies the number of spaces to substitue for a <span class="smallblock">TAB</span> character when parsing HTML input between &lt;pre&gt;...&lt;/pre&gt; tags. The default value (8) is consistent with the HTML specification, but many programs including Windows NotePad uses a value of 6.

# Values

<span class="parameter">$tabSpaces</span>

**Values**

Integer value greater than 0

<span class="smallblock"></span><span class="smallblock">DEFAULT</span>: 8

# Examples

Example #1

{% highlight php %}
<?php

$mpdf = new \Mpdf\Mpdf();

$mpdf->tabSpaces = 6;

$html = file_get_content('NotePad.txt');

$mpdf->WriteHTML('
'.$html.'</pre>');

$mpdf->Output();

?>
{% endhighlight %}

<p><span class="jslink">

</span>

