---
redirect_from:
  - "/overview/overview"
interact_link: content/Overview/Overview.ipynb
kernel_name: python3
has_widgets: false
title: 'Overview'
prev_page:
  url: 
  title: ''
next_page:
  url: /Prerequisites/overview
  title: 'Prerequisites'
comment: "***PROGRAMMATICALLY GENERATED, DO NOT EDIT. SEE ORIGINAL FILES IN /content***"
---

<section class="doc-section" id="section-7930">
<h3>Tool Development Process</h3>

<div class="doc-content" data-id="7930">
<p>Each hub relies on its user community to upload tools and other resources. Hubs are normally configured to allow any user to upload a tool. The process starts with a particular user filling out a web form to register his intent to submit a tool. This tells the hub manager to create a new project area for the tool. The user then uploads code into a <a href="https://subversion.apache.org">Subversion</a> source code repository, and develops the code within a workspace. The user can work alone or with a team of other users. When the tool is ready for testing, the hub manager installs the tool and asks the development team to approve it. Then, the hub manager takes one last look at the tool, and if everything looks good, moves the tool to the &quot;published&quot; state. Of course, a tool can be improved even after it is published, and re-installed, approved, and published over and over again.</p>

<p>The complete process is explained in the <a href="/documentation/{{version}}/managers/maintenance.tools">tool maintenance documentation for hub managers</a>. Additional details about this process can be found in the following seminars:</p>

<ul>
	<li><a href="https://nanohub.org/resources/14671" rel="external">Bootcamp Course for New Developers</a></li>
	<li><a href="https://nanohub.org/resources/14668" rel="external">Overview of Tool Development Process</a></li>
	<li><a href="http://nanohub.org/resources/3081" rel="external">Using Workspaces</a></li>
	<li><a href="https://nanohub.org/resources/14669" rel="external">Using Subversion for Source Code Control</a></li>
</ul>

<p class="note">The tool contribution process currently only supports Subversion (SVN). We are investigating support for <a href="https://git-scm.com">Git</a> but there is no timeline for availability.</p>
</div>
</section>

<section class="doc-section" id="section-7931">
<h3>Creating Graphical User Interfaces</h3>

<div class="doc-content" data-id="7931">
<p>If a tool already has a graphical user interface that runs under Linux/X11, then it can be published as-is, usually in a matter of hours. There are two caveats:</p>

<ul>
	<li><b>If the tool relies heavily on graphics, it may not perform very well within HUBzero execution containers.</b> Our containers run in cluster nodes without graphics cards, and are therefore configured with MESA for software emulation of OpenGL. This has much poorer performance than ordinary desktop computers with a decent graphics card, so frame rates are much lower. Also, all graphics are transmitted to the user&#39;s web browser after rendering, again lowering the frame rate. You can expect to achieve a few frames per second in the hub environment--good enough to view and interact with the data, but far below 100 frames/sec that you would normally see on a desktop computer.</li>
	<li><b>Tools running within the hub have access to the hub&#39;s local file system--not the user&#39;s desktop.</b> Many tools have a <i>File</i> menu with an <i>Open</i> option. When a user invokes this option within the hub environment, it will bring up a file dialog showing the hub file system. The user won&#39;t see his own local files there unless he uploads them first via sftp, webdav, or the hub&#39;s <code>importfile</code> command.</li>
</ul>

<p>The graphical user interface for any tool published in the hub environment can be created using standard toolkits for desktop applications--including Java, Matlab, Python/QT, etc.</p>

<p>If you&#39;re looking for an easy way to create a graphical interface for a legacy tool or simple modeling code, check out the <a href="http://rappture.org">Rappture Toolkit</a> that is included as part of HUBzero. Rappture reads a simple XML-based description of a tool and generates a graphical user interface automatically. It interfaces naturally with many programming languages, including C/C++, Fortran, Matlab, Python, Perl, Tcl/Tk, and Ruby. It creates tools that look something like the following:</p>

<p class="img-wrap"><img alt="example of a Rappture-based tool" src="rappture_01.png" /></p>

<p>&nbsp;</p>

<p>Rappture was designed for the hub environment and therefore addresses the caveats listed above. All Rappture-based tools have integrated visualization capabilities that take advantage of hardware-accelerated rendering available on the HUBzero rendering farm. Rappture-based tools also include options to upload/download data from the end user&#39;s desktop via the <code>importfile</code>/<code>exportfile</code> commands available within HUBzero.</p>

<p>For more details about Rappture, see the following links:</p>

<ul>
	<li><a href="https://nanohub.org/infrastructure/rappture/wiki/whatIsRappture" rel="external">Rappture Quick Overview</a></li>
	<li><a href="/resources/tooldev" rel="external">Developing Scientific Tools for the HUBzero Platform</a> (introductory course with 7 lectures)</li>
	<li><a href="https://nanohub.org/infrastructure/rappture/wiki/Documentation" rel="external">Rappture Reference Manual</a></li>
</ul>
</div>
</section>

<section class="doc-section" id="section-7932">
<h3>Learn more about HUBzero Tools</h3>

<div class="doc-content" data-id="7932">
<p>Discover the power of HUBzero tools and how easy it is to visualize research using the HUBzero platform.</p>

<p style="text-align: center;">Jupyter Notebooks:</p>

<p align="center"><iframe allowfullscreen="" frameborder="0" height="315" src="https://www.youtube.com/embed/_JM3sBA0Imc" width="560"></iframe></p>

<p>&nbsp;</p>

<p style="text-align: center;">RStudio:</p>

<p style="text-align: center;"><iframe allowfullscreen="" frameborder="0" height="315" src="https://www.youtube.com/embed/vU1-69-pPyI" width="560"></iframe></p>

<hr />
<p>Check out custom software and tool projects the HUBzero development team has helped design and implement on sites using the HUBzero platform.&nbsp;</p>

<p align="center">REMEDI Central:</p>

<p align="center"><iframe allowfullscreen="" frameborder="0" height="315" src="https://www.youtube.com/embed/YB4MiQOe_yk" width="560"></iframe></p>
</div>
</section>




{:.input_area}
```python
# HIDDEN
url="https://www.youtube.com/embed/S_f2qV2_U00?rel=0&amp;controls=0&amp;showinfo=0"
IFrame(url, width=560, height=315)
```





<div markdown="0" class="output output_html">

        <iframe
            width="560"
            height="315"
            src="https://www.youtube.com/embed/S_f2qV2_U00?rel=0&amp;controls=0&amp;showinfo=0"
            frameborder="0"
            allowfullscreen
        ></iframe>
        
</div>


