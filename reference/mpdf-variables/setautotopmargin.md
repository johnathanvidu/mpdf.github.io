---
layout: page
title: setAutoTopMargin
parent_title: mPDF Variables
permalink: /reference/mpdf-variables/setautotopmargin.html
modification_time: 2015-08-05T12:02:25+00:00
---

(mPDF >= 4.0)

# Description

mixed **setAutoTopMargin**

Specify the behaviour defining the top-margin of the document. When <span class="parameter">$setAutoTopMargin</span> is set to 'stretch' then <span class="parameter">$autoMarginPadding</span> defines the minimum distance in mm that will be forced between the bottom of the header and the top of the main text.

# Values

<span class="parameter">$setAutoTopMargin</span>

**Values**

pad - the value for margin-top is used to set a fixed distance in mm (padding) between the bottom of the header and top of the main text

stretch -  margin-top sets a **minimum** distance in mm between the top of the page and the top of the main text, which expands if header is too large to fit.

<span class="smallblock">FALSE</span> - the defined value for margin-top is respected even if the header overlaps the main body of the document.

<span class="smallblock">DEFAULT</span> <span class="smallblock">FALSE</span>

# See Also

<ul>
<li class="manual_boxlist"><a href="{{ "/headers-footers/headers-top-margins.html" | prepend: site.baseurl }}">Headers &amp; Top margins </a></li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/setautobottommargin.html" | prepend: site.baseurl }}">setAutoBottomMargin</a> -Specify mode of determining bottom-margin position</li>
<li class="manual_boxlist"><a href="{{ "/reference/mpdf-variables/automarginpadding.html" | prepend: site.baseurl }}">autoMarginPadding</a> - Specify padding between top-margin and header in automatic mode</li>
</ul>

