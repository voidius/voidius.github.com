---
layout: entry
title: Better fonts rendering in OS X 10.7
---

Play a little bit with the -int parameter (1..4)

{% highlight bash %}
$ defaults -currentHost write -globalDomain AppleFontSmoothing -int 1
{% endhighlight %}

This command also works for 10.8, but it already has nice font rendering out of the box.
