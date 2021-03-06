---
layout: page
title: Installation v7.x
parent_title: Installation & Setup
permalink: /installation-setup/installation-v7-x.html
modification_time: 2017-03-08T10:02:23+02:00
---

# Installation

Official installation method is via composer and its packagist package [mpdf/mpdf](https://packagist.org/packages/mpdf/mpdf).

{% highlight terminal %}
$ composer require mpdf/mpdf
{% endhighlight %}

# Usage

The simplest usage of the library would be as follows:

{% highlight php %}
<?php

require_once __DIR__ . '/vendor/autoload.php';

$mpdf = new \Mpdf\Mpdf();
$mpdf->WriteHTML('<h1>Hello world!</h1>');
$mpdf->Output();
{% endhighlight %}

All [configuration directives](https://mpdf.github.io/reference/mpdf-variables/overview.html) can
be set by the `$config` parameter of the constructor.

It is recommended to set custom temporary directory via `tempDir` configuration key.
The directory must have write permissions (mode `775` is recommended).

If you have problems, please read the section on
<a href="{{ "/troubleshooting/known-issues.html" | prepend: site.baseurl }}">troubleshooting</a> in the manual.

# Upgrading from older mPDF versions

mPDF 7.x has introduced namespaces, so in order to use mPDF, you have to reference the class either by fully
qualified name:

{% highlight php %}
<?php

require_once __DIR__ . '/vendor/autoload.php';

$mpdf = new \Mpdf\Mpdf();
{% endhighlight %}

or import the class beforehand:

{% highlight php %}
<?php

use Mpdf\Mpdf;

require_once __DIR__ . '/vendor/autoload.php';

$mpdf = new Mpdf();
{% endhighlight %}

The class now accepts only one parameter, an array of configuration directives. See
[configuration directives](https://mpdf.github.io/reference/mpdf-variables/overview.html) for reference.

If you wish to install additional fonts please see the notes in
<a href="{{ "/fonts-languages/fonts-in-mpdf-7-x.html" | prepend: site.baseurl }}">Fonts &amp; Languages</a>
for further instructions.
