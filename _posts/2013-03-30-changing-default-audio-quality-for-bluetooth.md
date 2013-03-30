---
layout: entry
title: Changing the Default Audio Quality for Bluetooth Headphones
---
To increase the quality, it’s as easy as entering this in Terminal:

{% highlight bash %}
defaults write com.apple.BluetoothAudioAgent "Apple Bitpool Min (editable)" 50
{% endhighlight %}

By default it is set to 2

This setting is stored in `~/Library/Preferences/com.apple.BluetoothAudioAgent` file. So you are able to open this file in `.plist` editor to change the setting as well.