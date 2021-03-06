<h1>Completing a Data Transfer</h1>

        
<br>
When you switch to a different type of slot, we will gladly transfer your files from the old server to the new one. Simply <a href="https://www.feralhosting.com/manager/tickets/new">raise a ticket</a> to have this done for you. Please title the ticket <code>Data Transfer Request</code>.<br>
<br>
Everything will be copied over to the new server recursively. This includes your data, <code>.torrents</code>, and other files. Your directory structure will also be preserved.<br>
<br>
As soon as your new slot is active, please use the <code>Install Software</code> link in your <a href="https://www.feralhosting.com/manager/">Account Manager</a> to install software on the new server in preparation for completing the data transfer.<br>
<br>
We will update the ticket as soon as the transfer is complete (you will also be automatically notified by email). Depending on the amount of data to transfer, it might take anywhere from a few hours to a couple of days.<br>
<br>
When the transfer is complete you will find your files under your home directory <code>~&#x2F;</code> on the new server in a folder named:<br>
<br>
<pre><code>~&#x2F;data-from-server</code></pre><br>
Where <code>server</code> in <code>data-from-server</code> is the name of your old server. For example:<br>
<br>
<pre><code>~&#x2F;data-from-aphrodite</code></pre><br>
What you will find below this directory is a complete mirror of your old slot with its directory structure preserved.<br>
<br>
 <strong>Important note:</strong> Your torrents will not be automatically seeding after the transfer on the new slot. You will need to:<br>
 <br>
 <strong>1:</strong> Install a torrent client(s) using the <code>Install Software</code> link in your <a href="https://www.feralhosting.com/manager/">Account Manager</a>.<br>
 <br>
 <strong>2:</strong> Move your data and <code>.torrents</code> to the right locations on the server.<br>
<br>
There is a certain amount of risk involved in this operation in the sense that in some cases your torrent client will fail to locate the data for certain <code>.torrents</code> and will attempt to re-download from the tracker. Which is why we recommend:<br>
<br>
<strong>You throttle your torrent client&#x27;s download speed to the lowest possible value (1 KB&#x2F;s) before you move data and <code>.torrents</code></strong><br>
<br>
<h2>rTorrent &#x2F; ruTorrent</h2><br>
<h3>Rutorrent: throttle your download.</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/rutorrent.png"><br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> to your new server and execute the following commands in this particular order:<br>
<br>
<h3>Move the rTorrent Data</h3><br>
The move command:<br>
<br>
<pre><code>mv ~&#x2F;data-from-server&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;* ~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
Optional: The copy command if needed:<br>
<br>
<pre><code>cp -rf ~&#x2F;data-from-server&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;. ~&#x2F;private&#x2F;rtorrent&#x2F;data</code></pre><br>
Substitute <code>server</code> in <code>data-from-server</code> with the name of your old server.<br>
<br>
<h3>Move the the rTorrent .torrents</h3><br>
The move command:<br>
<br>
<pre><code>mv ~&#x2F;data-from-server&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch</code></pre><br>
Optional: The copy command if needed:<br>
<br>
<pre><code>cp -rf ~&#x2F;data-from-server&#x2F;private&#x2F;rtorrent&#x2F;work&#x2F;*.torrent ~&#x2F;private&#x2F;rtorrent&#x2F;watch</code></pre><br>
Substitute <code>server</code> in <code>data-from-server</code> with the name of your old server.<br>
<br>
Warning: Make certain that your default download directory is set to the default location <code>~&#x2F;private&#x2F;rtorrent&#x2F;data&#x2F;</code>. Otherwise you will need to move all of the torrent data to the location you have it set to. If not, the client will be unable to locate the data, and begin downloading new data.<br>
<br>
<strong>Important Note:</strong> What to expect during the process.<br>
<br>
When you first issue the command to move or copy the <code>torrent</code> files into the watch directory, you will begin to see the torrents appear in the ruTorrent Web GUI, in the Download section (select from top left-hand side of GUI). At this point the rTorrent client is processing your torrents and checking for its data. Once it has processed a torrent and identified its data, it will show as 100% complete and seeding, and will move the torrent out of the Downloading section of the GUI. <br>
<br>
It is important to keep in mind, when you move many torrents into the rtorrent watch directory, the processing and checking of each torrent and its associated data will take a fair amount of time. Be patient while this is happening. Adding 200 torrents, for example, will take approximately 10 minutes for everything to be processed and for the GUI to reflect this.<br>
<br>
<h2>Deluge</h2><br>
<h3>Deluge: throttle your download.</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/deluge.png"><br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> to your new server and execute the following commands in this particular order:<br>
<br>
<h3>Move the Deluge Data</h3><br>
The move command:<br>
<br>
<pre><code>mv ~&#x2F;data-from-server&#x2F;private&#x2F;deluge&#x2F;data&#x2F;* ~&#x2F;private&#x2F;deluge&#x2F;data</code></pre><br>
Optional: The copy command if needed:<br>
<br>
<pre><code>cp -rf ~&#x2F;data-from-server&#x2F;private&#x2F;deluge&#x2F;data&#x2F;. ~&#x2F;private&#x2F;deluge&#x2F;data</code></pre><br>
Substitute <code>server</code> in <code>data-from-server</code> with the name of your old server.<br>
<br>
<h3>Move the the Deluge .torrents</h3><br>
The move command:<br>
<br>
<pre><code>mv ~&#x2F;data-from-server&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch</code></pre><br>
Optional: The copy command if needed:<br>
<br>
<pre><code>cp -rf ~&#x2F;data-from-server&#x2F;.config&#x2F;deluge&#x2F;state&#x2F;*.torrent ~&#x2F;private&#x2F;deluge&#x2F;watch</code></pre><br>
Substitute <code>server</code> in <code>data-from-server</code> with the name of your old server.<br>
<br>
<h2>Transmission</h2><br>
<h3>Transmission: throttle your download.</h3><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/transmission 1.png"><br>
<img src="https://raw.github.com/feralhosting/feralfilehosting/master/Feral%20Wiki/General/Completing%20a%20data%20transfer/transmission 2.png"><br>
<br>
<a href="https://www.feralhosting.com/faq/view?question=12">SSH</a> to your new server and execute the following commands in this particular order:<br>
<br>
<h3>Move the Transmission Data</h3><br>
The move command:<br>
<br>
<pre><code>mv ~&#x2F;data-from-server&#x2F;private&#x2F;transmission&#x2F;data&#x2F;* ~&#x2F;private&#x2F;transmission&#x2F;data</code></pre><br>
Optional: The copy command if needed:<br>
<br>
<pre><code>cp -rf ~&#x2F;data-from-server&#x2F;private&#x2F;transmission&#x2F;data&#x2F;. ~&#x2F;private&#x2F;transmission&#x2F;data</code></pre><br>
Substitute <code>server</code> in <code>data-from-server</code> with the name of your old server.<br>
<br>
<h3>Move the the Transmission .torrents</h3><br>
The move command:<br>
<br>
<pre><code>mv ~&#x2F;data-from-server&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch</code></pre><br>
Optional: The copy command if needed:<br>
<br>
<pre><code>cp -rf ~&#x2F;data-from-server&#x2F;.config&#x2F;transmission-daemon&#x2F;torrents&#x2F;*.torrent ~&#x2F;private&#x2F;transmission&#x2F;watch</code></pre><br>
Substitute <code>server</code> in <code>data-from-server</code> with the name of your old server.<br>
<br>
<h2>Final Steps</h2><br>
After you are done moving your data and <code>.torrents</code>, your torrent client will re-hash the data and start seeding. Depending on the amount of data to re-hash, this might take some time.<br>
<br>
Once all of your <code>.torrents</code> are seeding, do not forget to un-throttle your torrent client&#x27;s download speed (set it back to <code>off</code> or <code>unlimited</code>).<br>
<br>
