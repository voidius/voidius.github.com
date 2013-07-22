---
layout: entry
title: Copy file to clipboard buffer from terminal (OS X)
---

Copy to clipboard:
{% highlight bash %}
$ cat somefile.txt | pbcopy
{% endhighlight %}

Dump clipboard to file:
{% highlight bash %}
$ pbpaste > file.txt
{% endhighlight %}
