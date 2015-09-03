---
layout:     post
title:      How I Learned To Stop Kvetching and Finally Love Git
date:       2015-09-02 15:09:41
summary:    It was invisible and kept throwing me errors, so why do so many developers swear by it?
categories: ruby rails git
comments:   true
---

No coding bootcamp promotes Git as one of the languages or frameworks that they teach.  No one I've met at a MeetUp boasts specialized knowledge of or expertise in Git. In the Indeed.com search bar, typing 'Git' is not immediately recognized and does not have an auto-complete, like the way 'Ruby' does for 'Ruby on Rails.'

So why do I have to learn it to become a Web developer?

![The Git website](http://i60.tinypic.com/244o2oi.jpg)

Though I've been forced to install Git for online tutorials and courses, and learn basic functionality, it took me awhile but I finally realized why:  Git is the fundamental platform for dynamically publishing code to GitHub, as well as sharing and tracking your work in a team-based environment.

It's for better workflow and process, part of becoming a developer with a real job, project, or client. Git is one of the most important tools and resources that a programmer needs -- but no one will tell you that you must master the fundamentals or else you'll be left out.

I got it.

But I didn't get it, because it kept throwing me errors, and I often couldn't continue with a project because I had to resolve the Git issue first.  Argh.

One of the biggest errors I used to get was when I was ready to push a branch to GitHub:

```
git push origin
```

which would deliver

```
fatal: The current branch <branch_name> has no upstream branch.
To push the current branch and set the remote as upstream, use
```

```
    git push --set-upstream origin <branch_name>
```


This used to rack my brain until I finally figured out that I needed to simply include

```
git push origin <branch_name>
```

and all would be OK.

Another small discovery was ```git pull```.  It kept throwing me errors until I realized that I needed to make sure I was in the same branch locally that I was pulling from from GitHub.

<h3>Resources</h3>
The Git website actually has *the entire ProGit book* available for [free](http://git-scm.com/book/en/v2), for download and in multiple formats.  Why [spend](http://www.amazon.com/Pro-Git-Scott-Chacon/dp/1484200772?ie=UTF8&camp=1789&creative=9325&creativeASIN=1430218339&linkCode=as2&tag=git-sfconservancy-20) the $40 on Amazon?

But to be honest, it was  bit overwhelming for a newbie like me.  My [Bloc](https://www.bloc.io/web-development-bootcamp) mentor Brittany Martin suggested a great Git resource, [FirstAidGit](http://www.firstaidgit.io), which has a great search function.  When I couldn't find something, I even [tweeted](http://twitter.com/magalhini) the site's creator and he responded promptly.

But of course, as with all error messages, what does any true programmer do in the heat of the moment?  Why Google the error message, of course!

<h3>Learning by Breaking Things</h3>
Funny story, I didn't really break anything other than my patience or ego, but some of you may have had this same experience when you first learned to code:  A few times, I would push a branch to GitHub, then switch the branch on the command line.  

I would then go back to the text editor -- I was using Sublime Text at the time (btw, please someone out there, tell me I am NOT the only junior developer who paid $70 for the full license to Sublime!) -- and exclaim, Holy @#$%&!, What happened to my other version? It was gone! 

I would freak out, get frustrated, break a sweat, and then -- yes, you guessed it -- *re-enter all of the changes* to make it look like the version I thought I lost, and then save.

It was like in the olden days of Microsoft Word when your new version wasn't saved and you had to rely on your handwritten notes to re-create what you thought you lost.

About 1.5 months went by when I was inadvertently switching between branches and noticed lightning-fast changes in Sublime. And then I had one of those developer a-ha moments and realized, 'Now I understand what Git does!'  Apparently, behind the scenes, Git is keeping a stash of all previous versions if those versions are saved as individual branches.

But I think one of the reasons why Git was so confusing and opaque was because I had no idea where all of these branches or previous versions were stored. In my hard drive, apparently. Switching to the Atom editor makes this a lot clearer, as sitting right there, first on the list, is the .git folder.  

![Git folder in Atom](http://i61.tinypic.com/21ki2hu.jpg)

I plan on sharing some additional Git discoveries as I continue my coding journey.  If you have any particular Git 'hacks,' [let me know!]({{ site.baseurl }}/contact/)
