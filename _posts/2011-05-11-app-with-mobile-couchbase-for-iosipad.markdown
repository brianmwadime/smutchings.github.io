---
layout: post
title: App with Mobile CouchBase for iOS/iPad
date: 2011-05-11 13:13:56.000000000 +02:00
---
<h3>Update</h3>
The Mobile Couchbase team recently updated the project files and documentation to use MobileCouchbase in your own Apps. You can find the documentation <a href="https://github.com/couchbaselabs/iOS-Couchbase/blob/master/doc/using_mobile_couchbase.md">on GitHub</a>.

<del datetime="2011-05-20T13:02:12+00:00">It took me two days to get the mobile CouchBase running in Xcode 4. So here's how it works:

<del datetime="2011-05-20T13:02:12+00:00"><strong>Important:</strong> Do not build or run the project until you have set it up completely!
</del>
<ul>
	<li><del datetime="2011-05-20T13:02:12+00:00">Get the latest CouchBase repository from <a href="https://github.com/couchbaselabs/iOS-Couchbase/">https://github.com/couchbaselabs/iOS-Couchbase/</a></del></li>
	<li><del datetime="2011-05-20T13:02:12+00:00">Open Xcode</del></li>
	<li>C<del datetime="2011-05-20T13:02:12+00:00">reate a new project. I used the Split View-based Application. Make sure "Use Core Data" and the initialization of the git repository is checked.</del> <img src="http://patrickheneise.me/wp-content/uploads/2011/05/Screen-shot-2011-05-11-at-12.30.52-300x202.png" alt="" title="Screen shot 2011-05-11 at 12.30.52" width="300" height="202" class="aligncenter size-medium wp-image-312" /></li>
	<li><del datetime="2011-05-20T13:02:12+00:00">Add CFNetwork.framework from the iOS system frameworks and the DatabaseManager.h / DatabaseManager.m to your project in Xcode.</del> <img src="http://patrickheneise.me/wp-content/uploads/2011/05/Screen-shot-2011-05-11-at-12.36.29-197x300.png" alt="" title="Screen shot 2011-05-11 at 12.36.29" width="197" height="300" class="aligncenter size-medium wp-image-313" /></li>
	<li><del datetime="2011-05-20T13:02:12+00:00"><code>#import "DatabaseManager.h"</code> in your application delegate</del></li>
	<li><del datetime="2011-05-20T13:02:12+00:00">Now it get's a bit tricky. You need to get the source code for three libraries. Open your development root folder and type the following commands:</del> 
<del datetime="2011-05-20T13:02:12+00:00"><pre>git submodule add git@github.com:TouchCode/TouchJSON.git /Vendor/TouchJSON
git submodule add https://github.com/schwa/trundle.git /Vendor/trundle
git submodule add https://github.com/TouchCode/TouchFoundation.git /Vendor/TouchFoundation</pre></del></li>
	<li><del datetime="2011-05-20T13:02:12+00:00">Open the Finder and locate the "Source" directories for each library and copy the directory into Xcode (<strong>ONLY</strong> the directory within these library called "Source". You can rename them in the Xcode browser according to their library-names after copying them. Make sure "Copy items into destination group's folder" is checked, and "Create groups for any added folders" is active).</del> <img src="http://patrickheneise.files.wordpress.com/2011/05/screen-shot-2011-05-11-at-13-03-37.png" alt="" title="Screen shot 2011-05-11 at 13.03.37" width="218" height="171" class="aligncenter size-full wp-image-319" /></li>
</ul>

<del datetime="2011-05-20T13:02:12+00:00"><strong>Build succeeded.</strong> :)</del>

<h2><del datetime="2011-05-20T13:02:12+00:00">Update</del></h2>
<p><del datetime="2011-05-20T13:02:12+00:00">I forgot to implement "Couchbase.h", and after putting <code>#import "Couchbase.h"</code> into the Delegate, the whole thing didn't compile anymore.</del></p>

<del datetime="2011-05-20T13:02:12+00:00">The solution is as following:
Create a folder and include your project and the Couchbase-folder. Now create a Workspace and copy your project file (xcodeproj) and the Couchbase.xcodeproj into the workspace in Xcode. Copy the "Couchbase.h" into the Libraries-folder of your project and it should compile. From this point you can start creating your CouchBase app.</del>

<del datetime="2011-05-20T13:02:12+00:00">I had a lot of problems with linker errors complaining about i386 and armv7 missing links etc. Make sure you have the right schema (iPad simulator) and the right valid architectures "armv6 armv7". Cleaning the project doesn't always help in this case, so find your "DerivedData"-folder (usually ~/Library/Developer/Xcode/DerivedData) and delete the entire project folder. Then rebuild the project again.</del>
