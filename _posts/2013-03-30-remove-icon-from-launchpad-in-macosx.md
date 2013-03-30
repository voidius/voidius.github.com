---
layout: entry
title: Remove icon from Launchpad in Mac OS X
---
Launch Terminal and enter the following command, replacing “APPNAME” with the name of the application you want to remove from Launchpad:

{% highlight bash %}
sqlite3 ~/Library/Application\ Support/Dock/*.db "DELETE from apps WHERE title='APPNAME';" && killall Dock
{% endhighlight %}

For example, removing TmpDisk would be:

{% highlight bash %}
sqlite3 ~/Library/Application\ Support/Dock/*.db "DELETE from apps WHERE title='TmpDisk';" && killall Dock
{% endhighlight %}

Launchpad will automatically refresh, open it to see the changes.