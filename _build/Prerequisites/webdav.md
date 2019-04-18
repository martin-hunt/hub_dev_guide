---
redirect_from:
  - "/prerequisites/webdav"
interact_link: content/Prerequisites/webdav.ipynb
kernel_name: python3
has_widgets: false
title: 'WEBDAV'
prev_page:
  url: /Prerequisites/sftp
  title: 'SFTP'
next_page:
  url: /Process/process
  title: 'Process'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<h2>WebDAV</h2>

<div class="doc-content" data-id="7933">
<p>WebDAV is the Distributed Authoring and Versioning extension to the standard HTTP/HTTPS web protocol. It allows a client to browse a remote filesystem, usually with a graphical browser that makes it appear that your files are on your desktop. You may access your hub storage using only the secure version of this service (HTTPS). We do not support HTTP. Most modern computer platforms support HTTPS transport for WebDAV with either small adjustments or freely available software.</p>

<h3>Linux</h3>

<p>If you use the KDE graphical desktop environment, you can access your hub storage with the Konqueror browser by typing the special URL <tt>webdavs://<tt>webdav.hubname</tt>.org/webdav/</tt> (open source: <tt>webdavs://<tt>hubname</tt>.org/webdav/) </tt>into the Location field of the browser. It will prompt you for your hub login and password. Thereafter, you traverse your home directory by clicking on folders and you can drag and drop files to your desktop.</p>

<p>For Cinnamon or other graphical desktops, you can use the file browser with webdav.&nbsp;&nbsp; In the location field, enter <strong>davs://username@yourhub.org/webdav</strong>.&nbsp;&nbsp;</p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;OR</p>

<p>From the menu, select &quot;Connect to Server&quot; and fill out the form.&nbsp; Be sure to select &quot;Secure WebDAV (HTTPS)&quot; and folder &quot;/webdav&quot;.&nbsp;<br />
<img alt="Connect Menu for Linux" src="https://help.hubzero.org/app/site/media/images/documentation/2.2.0/Connect_Menu_Linux.png" style="width: 314px; height: 235px; margin-top: 10px; margin-bottom: 10px;" /><img alt="" src="https://help.hubzero.org/app/site/media/images/documentation/2.2.0/Connect_Dialog_Linux.png" style="width: 314px; height: 235px; margin: 10px 50px;" /><br />
You can also use the <a href="http://savannah.nongnu.org/projects/davfs2" rel="external">davfs2</a> kernel module to mount your hub storage area as a local filesystem.</p>

<h3>Macintosh</h3>

<p>MacOS versions 10.4 and higher support HTTPS transport for WebDAV using the Finder.</p>

<ol>
	<li>Select the Go menu in the Finder and choose &quot;Connect to Network Server&quot;.</li>
	<li>Enter the URL <tt>https://<tt>webdav.hubname</tt>.org/webdav/ (open source:&nbsp;https://<tt>hubname</tt>.org/webdav/</tt> into the address field.</li>
	<li>When prompted, enter your <span class="who who-default">Network ID</span> credentials.</li>
</ol>

<p>You should now be able to drag files and folders between your computer and the site to which you just connected.</p>

<p>&nbsp;</p>

<h3>Windows 10</h3>

<p>The <b>WebClient Services</b> to connect to a WebDAV Servers, by default, the WebClient service is disabled, so we need to enable it.</p>

<ol>
	<li>From the <span class="menuitem">Start</span> menu, choose <span class="menuitem">Control Panel</span>, then <span class="menuitem">System and Security</span>, then <span class="menuitem">Administrative Tools</span>, and then <span class="menuitem">Services</span>.</li>
	<li>Scroll down to <span class="menuitem">WebClient</span>, set the service to <span class="menuitem">Automatic</span>, and then click <span class="menuitem">Apply</span>.</li>
	<li>If the service is not already running, click <span class="menuitem">Start</span>.</li>
	<li>Click <span class="menuitem">OK</span> to close the Control Panel and close other windows.</li>
</ol>

<p>To set up a WebDAV connection in Windows 10:</p>

<ol>
	<li>From the <b>Start Menu</b> go to <b>File Explorer </b>and select <b>This PC</b> on the left hand pane</li>
	<li>Select&nbsp;<b>Computer </b>from the top ribbon</li>
	<li>Click on <b>Map Network Drive</b></li>
	<li>Click <b>Connect to a Web site that you can use to store your documents and pictures.</b></li>
	<li>Click <b>Next</b></li>
	<li>Select<b> Choose another network location</b> and click <b>Next</b></li>
	<li>Enter &quot;<tt><strong>https://<tt>webdav.hubname</tt>.org/webdav/</strong>&quot; (open source<tt>: </tt><strong>https://<tt>hubname</tt>.org/webdav/</strong>)</tt>.&nbsp; Replace &quot;hubname.org&quot; with the URL of the destination hub and click <b>Next</b></li>
	<li>Enter your <b>password</b>, and click <b>Ok</b></li>
	<li>Click <b>Next</b>, then <b>Finish</b></li>
	<li>When prompted, enter your <span class="who who-default">Hub </span>credentials.</li>
	<li>You should see a new Network Drive under your Computer/This PC.&nbsp; Double click on it to open.</li>
</ol>

<p>You should now be able to drag files and folders between your computer and the hub via the network drive to which you just connected.</p>

<h3>Windows 8.x</h3>

<p>The <b>WebClient Services</b> to connect to a WebDAV Servers, by default, the WebClient service is disabled, so we need to enable it.</p>

<ol>
	<li>From the <span class="menuitem">Start</span> menu, choose <span class="menuitem">Control Panel</span>, then <span class="menuitem">System and Security</span>, then <span class="menuitem">Administrative Tools</span>, and then <span class="menuitem">Services</span>.</li>
	<li>Scroll down to <span class="menuitem">WebClient</span>, set the service to <span class="menuitem">Automatic</span>, and then click <span class="menuitem">Apply</span>.</li>
	<li>If the service is not already running, click <span class="menuitem">Start</span>.</li>
	<li>Click <span class="menuitem">OK</span> to close the Control Panel and close other windows.</li>
</ol>

<p>To set up a WebDAV connection in Windows 8.x:</p>

<ol>
	<li>Using the Search interface in tile mode, locate and select the <span class="menuitem">Computer</span> tile.</li>
	<li>In the quick menu at the top of the screen, click <span class="menuitem">Map Network Drive</span>.</li>
	<li>In the &quot;Folder&quot; field, enter a URL that points to the destination hub similar to the following URL &quot;<tt>https://<tt>webdav.hubname</tt>.org/webdav/&quot; (open source<tt>: </tt>https://<tt>hubname</tt>.org/webdav/)</tt>.&nbsp; Replace &quot;hubname.org&quot; with the URL of the destination hub.</li>
	<li>Select the <span class="menuitem">Connect using different credentials</span> box, and then click <span class="menuitem">Finish</span>.</li>
	<li>When prompted, enter your <span class="who who-default">Hub</span> credentials.</li>
	<li>You should see a new Network Drive under your Computer/This PC.&nbsp; Double click on it to open.</li>
</ol>

<p>You should now be able to drag files and folders between your computer and the hub via the network drive to which you just connected.</p>

<h3>Windows 7</h3>

<p>The <b>WebClient Services</b> to connect to a WebDAV Servers, by default, the WebClient service is disabled, so we need to enable it.</p>

<ol>
	<li>From the <span class="menuitem">Start</span> menu, choose <span class="menuitem">Control Panel</span>, then <span class="menuitem">System and Security</span>, then <span class="menuitem">Administrative Tools</span>, and then <span class="menuitem">Services</span>.</li>
	<li>Scroll down to <span class="menuitem">WebClient</span>, set the service to <span class="menuitem">Automatic</span>, and then click <span class="menuitem">Apply</span>.</li>
	<li>If the service is not already running, click <span class="menuitem">Start</span>.</li>
	<li>Click <span class="menuitem">OK</span> to close the Control Panel and close other windows.</li>
</ol>

<p>To set up a WebDAV connection in Windows 7.</p>

<ol>
	<li>From the <span class="menuitem">Start</span> menu, right-click <span class="menuitem">Computer</span>, and select <span class="menuitem">Map network drive.</span></li>
	<li>Enter a URL that points to the destination hub similar to the following URL &quot;<tt>https://<tt>webdav.hubname</tt>.org/webdav/&quot; (open source: https://<tt>hubname</tt>.org/webdav/)</tt>.&nbsp; Replace &quot;hubname.org&quot; with the URL of the destination hub.&nbsp; Clink finish.</li>
	<li>When prompted, enter your <span class="who who-default">Hub</span> credentials.</li>
	<li>You should see a new Network Drive under your Computer/This PC.&nbsp; Double click on it to open.</li>
</ol>

<p>You should now be able to drag files and folders between your computer and the hub via the network drive to which you just connected.</p>

<p>If you have difficulty dragging and dropping, right-click the file or folder you want to copy, and choose <span class="menuitem">Copy</span>. Then right-click the directory you want to put it in, and choose <span class="menuitem">Paste</span>.</p>
</div>

