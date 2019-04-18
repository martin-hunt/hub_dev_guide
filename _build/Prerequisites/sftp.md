---
redirect_from:
  - "/prerequisites/sftp"
interact_link: content/Prerequisites/sftp.ipynb
kernel_name: python3
has_widgets: false
title: 'SFTP'
prev_page:
  url: /Prerequisites/access
  title: 'Accessing Your Home Directory'
next_page:
  url: /Prerequisites/webdav
  title: 'WEBDAV'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<h2>SFTP</h2>

<div class="doc-content" data-id="7922">
<p><abbr title="Secure File Transfer Protocol">SFTP</abbr>, or Secure <abbr title="File Transfer Protocol">FTP</abbr>, is a program that uses SSH to transfer files. Unlike standard <abbr title="File Transfer Protocol">FTP</abbr>, it encrypts both commands and data, preventing passwords and sensitive information from being transmitted in the clear over the network. It is functionally similar to <abbr title="File Transfer Protocol">FTP</abbr>, but because it uses a different protocol, you can&#39;t use a standard <abbr title="File Transfer Protocol">FTP</abbr> client to talk to an S<abbr title="Secure File Transfer Protocol">FTP</abbr> server, nor can you connect to an <abbr title="File Transfer Protocol">FTP</abbr> server with a client that supports only S<abbr title="Secure File Transfer Protocol">FTP</abbr>.</p>

<p>The following tutorial should help you in using S<abbr title="Secure File Transfer Protocol">FTP</abbr> to connect to and from your HUBzero server(s).</p>

<p class="warning"><strong>Warning:</strong> Most accounts do <strong>not</strong> have <abbr title="Secure Shell">SSH</abbr>/S<abbr title="Secure File Transfer Protocol">FTP</abbr> access initially. Your system administrator must grant your account access before you will be able to connect.</p>

<h4>Graphical Clients</h4>

<p>Using graphical SFTP clients simplifies file transfers by allowing you to transmit files simply by dragging and dropping icons between windows. When you open the program, you will have to enter the name of the host (e.g., yourhub.org) and your HUB username and password.&nbsp;&nbsp;The use of graphical SFTP clients is highly recommended if you have access to it. &nbsp;Done properly they allow you to quickly and easily access your HUB files as if they are local files on your desktop.</p>

<h5>Linux</h5>

<ul>
	<li>From the file browser, type &quot;sftp://yourhub.org&quot;.&nbsp; Use the name of your hub instead of &quot;yourhub.org&quot;.&nbsp; If you don&#39;t see the location field at the top of the file browser window, hit Ctrl+L to toggle it.&nbsp; &nbsp;Your files will now be available through the file browser like local files.</li>
</ul>

<h5>Windows Clients</h5>

<ul>
	<li><a href="http://winscp.net/">WinSCP</a></li>
	<li><a href="http://www.bitkinex.com/sftpclient/">BitKinex</a></li>
	<li><a href="http://filezilla-project.org/">FileZilla</a></li>
	<li><a href="http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html">PuTTY</a></li>
</ul>

<h5>Mac OSX Clients</h5>

<ul>
	<li><a href="http://www.panic.com/transmit/">Transmit</a></li>
	<li><a href="http://fetchsoftworks.com/">Fetch</a></li>
	<li><a href="http://cyberduck.ch/">Cyberduck</a></li>
	<li><a href="http://extendmac.com/flow/">Flow</a></li>
	<li><a href="https://www.binarynights.com/forklift/">Forklift</a>Version2 is available for free through the app store.</li>
</ul>

<h5>Command-line</h5>

<p>You can use command line SFTP from Linux, or from your Mac OS X terminal. To start an SFTP session, at the command prompt, enter:</p>

<pre>
yourmachine:~ you$ sftp username@host
yourmachine:~ you$ username@host password:

<strong>host</strong> ~
</pre>

<table>
	<caption>Some standard commands for command-line S<abbr title="Secure File Transfer Protocol">FTP</abbr></caption>
	<thead>
		<tr>
			<th scope="col">Command</th>
			<th scope="col">Description</th>
		</tr>
	</thead>
	<tbody>
		<tr class="odd">
			<td><code>cd</code></td>
			<td>Change the directory on the remote computer</td>
		</tr>
		<tr class="even">
			<td><code>chmod</code></td>
			<td>Change the permissions of files on the remote computer</td>
		</tr>
		<tr class="odd">
			<td><code>chown</code></td>
			<td>Change the owner of files on the remote computer</td>
		</tr>
		<tr class="even">
			<td><code>dir</code> (or <code>ls</code>)</td>
			<td>List the files in the current directory on the remote computer</td>
		</tr>
		<tr class="odd">
			<td><code>exit</code> (or <code>quit</code>)</td>
			<td>Close the connection to the remote computer and exit SFTP</td>
		</tr>
		<tr class="even">
			<td><code>get</code></td>
			<td>Copy a file from the remote computer to the local computer</td>
		</tr>
		<tr class="odd">
			<td><code>help</code> (or <code>?</code>)</td>
			<td>Get help on the use of SFTP commands</td>
		</tr>
		<tr class="even">
			<td><code>lcd</code></td>
			<td>Change the directory on the local computer</td>
		</tr>
		<tr class="odd">
			<td><code>lls</code></td>
			<td>See a list of the files in the current directory on the local computer</td>
		</tr>
		<tr class="even">
			<td><code>lmkdir</code></td>
			<td>Create a directory on the local computer</td>
		</tr>
		<tr class="odd">
			<td><code>ln</code> (or <code>symlink</code>)</td>
			<td>Create a symbolic link for a file on the remote computer</td>
		</tr>
		<tr class="even">
			<td><code>lpwd</code></td>
			<td>Show the current directory (present working directory) on the local computer</td>
		</tr>
		<tr class="odd">
			<td><code>lumask</code></td>
			<td>Change the local umask value</td>
		</tr>
		<tr class="even">
			<td><code>mkdir</code></td>
			<td>Create a directory on the remote computer</td>
		</tr>
		<tr class="odd">
			<td><code>put</code></td>
			<td>Copy a file from the local computer to the remote computer</td>
		</tr>
		<tr class="even">
			<td><code>pwd</code></td>
			<td>Show the current directory (present working directory) on the remote computer</td>
		</tr>
		<tr class="odd">
			<td><code>rename</code></td>
			<td>Rename a file on the remote host</td>
		</tr>
		<tr class="even">
			<td><code>rm</code></td>
			<td>Delete files from the remote computer</td>
		</tr>
		<tr class="odd">
			<td><code>rmdir</code></td>
			<td>Remove a directory on the remote host (the directory usually has to be empty)</td>
		</tr>
		<tr class="even">
			<td><code>version</code></td>
			<td>Display the SFTP version</td>
		</tr>
		<tr class="odd">
			<td><code>&nbsp;!&nbsp;</code></td>
			<td>In Unix, exit to the shell prompt, where you can enter commands. Enter <code>exit</code> to get back to SFTP. If you follow <code>&nbsp;!&nbsp;</code> with a command (e.g., <code>!pwd</code>), SFTP will execute the command without dropping you to the Unix prompt.</td>
		</tr>
	</tbody>
</table>
</div>

