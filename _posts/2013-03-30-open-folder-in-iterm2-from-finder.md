---
layout: entry
title: Open folder in iTerm2 from Finder
---
We are going to create Service here. Go to Automator -> Service -> Run Applescript

copy+paste these lines and save:

{% highlight applescript %}
on run {input, parameters}
    tell application "Finder"
        set dir_path to "\"" & (POSIX path of (input as string)) & "\""
            -- display dialog dir_path
    end tell
    CD_to(dir_path)
end run

on CD_to(theDir)
    tell application "iTerm"
        activate
        try
            set t to the last terminal
        on error
            set t to (make new terminal)
        end try
        tell t
            launch session "Default Session"
            tell the last session
                write text "cd " & theDir & ";clear;ls"
            end tell
        end tell
    end tell
end CD_to
{% endhighlight %}

After that you will see a new entry on folder rightclick menu.

*code is not mine but stolen from somewhere*