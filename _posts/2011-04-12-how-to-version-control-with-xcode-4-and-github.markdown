---
layout: post
title: 'How To: Version control with Xcode 4 and GitHub?'
date: 2011-04-12 10:00:57.000000000 +02:00
---
As I'm going to build an iPad prototype for my graduation project and like to have it open source, I decided to go for GitHub (Online project hosting using Git. Includes source-code browser, in-line editing, wikis, and ticketing. Free for public open-source code.) since I have good experience with this service during my Ruby on Rails developments and it's now implemented in Xcode 4. However, the implementation is fairly buggy to work with a remote repository. There are two guides I found to set the repository up, but both didn't work completely, so here's my version which worked fine.

<ol>
	<li>Open Xcode</li>
	<li>Create a new Xcode project. In the dialogue for source control make sure the local git repository is checked and will be created</li>
	<li>Quit Xcode (command+Q)</li>
	<li>Go to GitHub.com (create a user, if you don't have one yet) and <a href="https://github.com/repositories/new">create a new repository</a></li>
	<li>Open your <a href="http://www.apple.com/macosx/what-is-macosx/apps-and-utilities.html#terminal">Terminal.app</a>, go to the project folder ("cd ~/YourDevelopments/YourProject" and follow the GitHub Global setup:</li>
	<li><ul>
		<li>git config --global user.name "Your Name"</li>
		<li>git config --global user.email your@email.com</li>
	</ul></li>
	<li>Follow the "Existing Git repo?" steps:</li>
	<li><ul>
		<li>git remote add origin git@github.com:yourGitHubusername/yourGitHubProject.git</li>
		<li>git push -u origin master</li>
	</ul></li>
	<li>Go back to GitHub and click "continue"</li>
	<li>Your source data should be uploaded there and listed with the message "Initial Commit"</li>
	<li>Open your Xcode project</li>
	<li>After changing some files (f.e. changing from iPhone to iPad app) go to File-&gt;Source Control-&gt;Commit and write a short info/documentation of what you did (f.e. "Changed to iPad App"). Make sure all items are ticked in the left browser and press "Commit"</li>
	<li>Go to File-&gt;Source Control-&gt;Push. There will be an error, that your username is not correct, just ignore that. Go to File-&gt;Source Control-&gt;Push again and press "Push". There will be an error saying the push was not successful, ignore that too and Push again (File-&gt;Source Control-&gt;Push, "Push". You should get a message that there are no uncommitted changes in the project</li>
	<li>Check the repository on GitHub, it should show the changes now</li>
</ol>

This is of course extremely buggy and not "the apple way", but I guess the next implementation will be more stable.

References:
<a href="http://lists.apple.com/archives/xcode-users/2011/Mar/msg00616.html">http://lists.apple.com/archives/xcode-users/2011/Mar/msg00616.html</a>
<a href="http://lists.apple.com/archives/xcode-users/2011/Mar/msg00617.html">http://lists.apple.com/archives/xcode-users/2011/Mar/msg00617.html</a>
<a href="http://peterszwach.blogspot.com/2011/03/github-xcode-4.html">http://peterszwach.blogspot.com/2011/03/github-xcode-4.html</a>
