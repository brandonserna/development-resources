# git commit messages

Imagine commit messages as a newsfeed for the project. Prioritize __why__ vs. __how__. The how is clear in the code.

![](https://cbea.ms/content/images/size/w2000/2021/01/git_commit_2x.png)

### What is important in a commit message?


Summarize the change. Help your team understand what is going on in the project it must be useful and valuable to the people that read it.

_Tips_ 

* describe what changed in the commit as clearly and succintly as possible

* avoid details and try to write the general idea of the change 


```git
# short example
Replace jQuery onReady listener with plain JS; »fixes #1357

# long example
commit eb0b56b19017ab5c16c745e6da39c53126924ed6
Author: Pieter Wuille <pieter.wuille@gmail.com>
Date:   Fri Aug 1 22:57:55 2014 +0200

   Simplify serialize.h's exception handling

   Remove the 'state' and 'exceptmask' from serialize.h's stream
   implementations, as well as related methods.

   As exceptmask always included 'failbit', and setstate was always
   called with bits = failbit, all it did was immediately raise an
   exception. Get rid of those variables, and replace the setstate
   with direct exception throwing (which also removes some dead
   code).

   As a result, good() is never reached after a failure (there are
   only 2 calls, one of which is in tests), and can just be replaced
   by !eof().

   fail(), clear(n) and exceptions() are just never called. Delete
   them.
```


### References

https://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html

https://cbea.ms/git-commit/