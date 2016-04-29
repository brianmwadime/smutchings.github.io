---
layout: post
title: Let's Zap Some Ghosts
date: '2013-11-18 15:05:46'
description: How can you use Zapier and Ghost together to back up your posts?
meta-description: How can you use Zapier and Ghost together to back up your posts?
---

What if you could take your posts from [Ghost](http://ghost.org) and share them wherever you need? What if you could do this without a single plugin, and for free? It sounds too good to be true, right, but it's not. 

[Zapier](http://zpr.io/Pq3v) lets you connect online services to each other (and it currently supports over 250 of them) using Zaps. Whilst Ghost is not, technically, on the list; it can be connected to Zapier using the RSS feed that your Ghost blog updates every time you create a post. Let's see what we can do with it!

## Get your RSS feed URL
Getting the address of your RSS feed couldn't be any easier. It's simply the URL of your blog, with /rss at the end. For example, the RSS feed for this blog is `http://blog.samhutchings.co/rss`. It's that easy.

## Let's Zap
First things first, you'll need to create a Zapier account, if you don't already have one. If you signup using this [link](http://zpr.io/Pq3v), we both get some extra free Tasks, meaning our Zaps can trigger until the cows come home. 

### Make a Zap

Once you're logged in, hit **Make a Zap!** in the menu bar.

![Zapier Header](http://samhutchings.co/wp-content/uploads/2013/11/Dashboard-header.png)

You'll be taken to a new screen, where you can make a new Zap. It'll be blank right now, like this: 

![Blank Zap](http://samhutchings.co/wp-content/uploads/2013/11/Blank-zap.png)

#### Triggers. Actions. Tasks. WTF?

Zapier has some terms that you may want to get familiar with. I'll summarise them for you, before we continue. 

**Trigger**: When creating a Zap you always need a Trigger. This tells the Zap when to go off. It could be when you tweet, or get an email, or when your Ghost RSS feed updates.

**Action**: When creating a Zap, you always need an Action. This tells the Zap what to do when the Trigger goes off. This could be send a tweet, update your MailChimp account, or text someone. 

**Zap**: A Zap is what you get when you combine a Trigger and an Action. By default, it triggers every 15 minutes.

**Task**: A task is used every time a Zap triggers. You get a certain number per month. You can pay to get more, or do certain actiosn from the *Get Free Tasks* page to get more. 

### Back to the Zap

Now you have a blank Zap, let's choose the Trigger and Action for this zap. For the Trigger, we're going to use RSS. For the Action, in this case, we're going to use Twitter. 

You'll notice two new dropdowns appear, one under the Trigger and one under the Action. In the left hand one, there is only one option - 'New item in Feed', select this. In the right hand one there are two options. We're going to use 'Create Tweet', as we don't need to add an image just now. 

You should have something that looks like this: 

![Trigger and Action chosen](http://samhutchings.co/wp-content/uploads/2013/11/Choose-a-Trigger-and-Action.png)

Click continue, and onwards we go. 

### Select your accounts

Zapier will now ask you to provide an RSS account. Just click Continue, as we give the RSS information later on. 

You'll now be asked for your Twitter account. If you've used Zapier before, your Twitter account may already be there. If so, go ahead and select it. 

If it isn't, or you want to add a new account, select 'Connect a different Twitter account'. You'll be presented with a popup. Fill-in the name you want to give this account, and select if you want to autofollow [@Zapier](http://www.twitter.com/Zapier) or not. 

![Add a Twitter Account](http://samhutchings.co/wp-content/uploads/2013/11/Add-Twitter.png)

Click Continue, and you'll be presented with the normal Twitter authentication process, which may ask for your Username and Password.

![Twitter Auth](http://samhutchings.co/wp-content/uploads/2013/11/Twitter-auth.png)

Once you've connect your account and tested it, click continue to provide the RSS information for Ghost. You'll need your RSS URL, I'm going to use `http://blog.samhutchings.co/rss` in this example. Just pop it in, and click continue. 

![RSS options](http://samhutchings.co/wp-content/uploads/2013/11/RSS-Trigger-options.png)

### The creative bit

Now's the fun bit, where you choose what you want your tweet to say when you publish a new blog post. You can type whatever you want, just make sure it's under 140 characters. If you want to add some information from the post, such as the title or a link, you can do so from the 'Insert RSS fields' dropdown at the top right of the text field. 

I've added the Title and Link to my tweet, as well as a little credit to Ghost for making it so easy to write and publish these posts. 

![Example message](http://samhutchings.co/wp-content/uploads/2013/11/Message.png)

### Test it. Name it. Ship it.

You'll now have the option to test your Zap. It will load the 3 latest items from your RSS feed, and let you send a tweet to make sure everything's working. Once you're happy it's working, hit continue. 

Now it's just a case of giving your Zap a name and turning it on. Every 15 minutes it'll check for new posts to your Ghost blog, and send a tweet to let all and sundry know you've written something new. 

How awesome's that?

## It's not just Tweets

Zapier supports over 250 services, and Twitter is just one of them. You can do so much more. You could:

* Save all your posts to Evernote
* Share to App.net, Buffer, Facebook Pages and more
* Email a link to your friends
* Keep a record of when you've published stuff on Google Calendar
* Much, much more.

### Thanks

Thank you for taking the time to read this post. I hope you've found it useful. If you've got feedback or suggestions, let me know on [Twitter](http://twitter.com/Smutchings).

And remember: When zapping ghosts, **don't cross the streams!**

*P.S. Want some extra free tasks? Remember to signup using this [link](http://zpr.io/Pq3v).*

*P.P.S. Feeling lazy? I've [shared my Zap](http://zpr.io/gzRA), so you just have to pop in your blog's URL and your Twitter account.*