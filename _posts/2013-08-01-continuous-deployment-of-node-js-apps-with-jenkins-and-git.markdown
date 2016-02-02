---
layout: post
title: Continuous deployment of node.js apps with Jenkins and Git
date: 2013-08-01 11:59:55.000000000 +02:00
---
First of all, thanks to carbonsilk for providing the first tutorial on <a href="http://www.carbonsilk.com/node/deploying-nodejs-apps/">how to configure automated deployment with Git and Jenkins</a>.

But things have changed since 2011 so I'd like to share my simplified setup on automated (continuous) deployment of node.js applications with forever, git and jenkins. I'm using BitBucket in the example, you can just exchange the hostname with github.com for github repositories.

<ul>
	<li>As root/sudo:</li>
</ul>
<pre>sudo apt-get install jenkins</pre>
(open port 8080 in your firewall)
<pre>sudo npm install -g express connect karma forever</pre>
<ul>
	<li>As user 'jenkins' (sudo su jenkins)</li>
</ul>
<pre>git config --global user.name 'Jenkins'
git config --global user.email 'info@yourapp.com'
ssh bitbucket.org -l git (add the server to the list of authorised hosts)
ssh-keygen -t rsa &amp;&amp; cat ~/.ssh/id_rsa.pub</pre>
<ul>
	<li>Jenkins Web (http://yourserver:8080)</li>
</ul>
<ol>
	<li>Manage Jenkins - Manage Plugins - Search 'Git' - Install GIT plugin</li>
	<li>Manage Jenkins - Configure System - Enable security - Jenkins's own user database (Allow signup) - Logged-in users can do anything</li>
	<li>Register your user (remove Allow signup afterwards in the config)</li>
	<li>Add Job - 'Build a free-style software project'</li>
	<li>Source Code Management: Git (Repository URL: git@bitbucket.org:team/project.git)</li>
	<li>'Check Trigger builds remotely' (e.g., from scripts) and add random long password.</li>
	<li>Execude Shell:<br />
<pre>npm install
npm update
forever stopall
BUILD_ID=dontKillMe NODE_ENV=production forever start app.js</pre></li>

<ul><li>Go to Git provider (BitBucket, GitHub) and add Jenkins Service.</li></ul>

Get your API token from jenkins in your user profile and add it to your git scm:

http://yourjenkinsname:abc123abc123abc123abc123@yourcoolnewappserver:8080/

Project name: your-app

Token: the-random-long-password-you-defined-in-jenkins

<strong>Done.<img src="http://patrickheneise.files.wordpress.com/2013/08/health-80plus.png" alt="health-80plus" width="32" height="32" class="aligncenter size-full wp-image-640" /></strong>
