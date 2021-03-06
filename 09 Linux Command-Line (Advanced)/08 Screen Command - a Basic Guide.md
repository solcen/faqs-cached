<h1>Screen Command - a Basic Guide</h1>

        
<h2>Basic screen switches</h2><br>
There are many more Screen options and switches. To read the built-in Linux manual for Screen, please type this in the shell: <br>
<br>
<pre><code>man screen</code></pre><br>
(While reading the man pages, you can move forward by a full page with the Space bar, or line by line with the Enter key.)<br>
<br>
<pre><code>screen</code></pre><br>
Run a new screen session. It opens a new session, with just a bash prompt.<br>
<br>
<pre><code>screen program_name</code></pre><br>
Run a new screen session and launches the program you specify.<br>
<br>
<pre><code>screen -t some_title</code></pre><br>
Run a new screen session, with the title <code>some_title</code>.<br>
<br>
<pre><code>screen -S session_name</code></pre><br>
Run a new screen session and specify a meaningful name for the session.<br>
<br>
<pre><code>screen -S session_name program_name</code></pre><br>
Run a new screen session and specify a meaningful name for the session and launch some program at the same time. <br>
<br>
<pre><code>screen -r</code></pre><br>
Reattach to a previously detached session (if there is more than one detached screen running, it will display a list).<br>
<br>
<pre><code>screen -ls</code></pre><br>
It will display a list of screen sessions running.<br>
<br>
<pre><code>exit</code></pre><br>
When typed inside a screen, it will terminate the current screen session.<br>
<br>
<h2>Nested Screen Sessions</h2><br>
It&#x27;s possible to get stuck in a nested screen session. A common scenario: you start an SSH session from within a screen session. Within the SSH session, you start screen. By default, the outer screen session that was launched first responds to <code>C-a</code> commands. To send a command to the inner screen session, use <code>C-a a</code>, followed by your command. <br>
<br>
For example:<br>
<br>
<pre><code>C-a a d</code></pre><br>
Detaches the inner screen session.<br>
 <br>
<pre><code>C-a a K</code></pre><br>
Kills the inner screen session. <br>
<br>
<h2>Usage Examples</h2><br>
<pre><code>screen -S my_htop htop</code></pre><br>
This will launch htop in a screen with the session being named <code>my_htop</code>, so if you need to reattach to it with <code>screen -r</code>, it will be more obvious which one it is.<br>
<br>
<pre><code>screen -R my_htop</code></pre><br>
If you used the -S switch to name the session, you can then reattach to it by specifying the session name after the -R switch. Useful if you have several sessions of screen running detached.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/Screen%20Command%20-%20a%20Basic%20Guide/1.jpg"><br>
<br>
<h2>Key Bindings while running screen (case sensitive!)</h2><br>
<pre><code>Ctrl-a c</code></pre><br>
Create a new window and switch to it.<br>
<br>
<pre><code>Ctrl-a d</code></pre><br>
detach from the current screen session, letting it run in the background.<br>
<br>
<pre><code>Ctrl-a k</code></pre><br>
Kill the current window, after confirmation.<br>
<br>
<pre><code>Ctrl-A&nbsp; DD</code></pre><br>
have screen detach and log you out. <br>
<br>
<pre><code>Ctrl-a Ctrl-a</code></pre><br>
Switch to other running screen window<br>
<br>
<pre><code>Ctrl-a n</code></pre><br>
Go to the next window.<br>
<br>
<pre><code>Ctrl-a p</code></pre><br>
Go to the previous window.<br>
<br>
<pre><code>Ctrl-a w</code></pre><br>
Show a list of windows.<br>
<br>
<pre><code>Ctrl-a S</code></pre><br>
Split the current window in two.<br>
<br>
<pre><code>Ctrl-a Q</code></pre><br>
Close split screen. (It will kill the split section currently <strong>not</strong> in focus)<br>
<br>
<pre><code>Ctrl-a TAB</code></pre><br>
Move between split sections of the screen.<br>
<br>
<pre><code>Ctrl-a A</code></pre><br>
Give the the current window a name.<br>
<br>
<pre><code>Ctrl-a &quot;</code></pre><br>
List all windows - move around to change the window with the arrow keys.<br>
<br>
<pre><code>Ctrl-a F</code></pre><br>
Resize the window to the current region size.<br>
<br>
<pre><code>Ctrl-a ESC</code></pre><br>
 <br>
Enter scrollback mode. Use your arrow keys to move up and down inside your screen session. <br>
<br>
<h2>Usage Examples - Split Screen</h2><br>
To run two screen sessions in a split window, first start a screen with<br>
<br>
<pre><code>screen</code></pre><br>
(You can give it a session name with <code>-S</code> if you want)<br>
<br>
Then you should see a bash prompt.&nbsp; The session name by default is <code>bash</code>.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/Screen%20Command%20-%20a%20Basic%20Guide/2.jpg"><br>
<br>
Start another screen session inside the first screen, with<br>
<br>
<pre><code>screen</code></pre><br>
(Again, you can give it a session name with <code>-S</code> if you want)<br>
<br>
You can now switch between the two active screens with <code>Ctrl-a Ctrl-a</code> or <code>Ctrl-a n</code>.<br>
You can view a list of opened sessions with <code>Ctrl-a w</code>.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/Screen%20Command%20-%20a%20Basic%20Guide/3.jpg"><br>
<br>
Now let&#x27;s split one of those screens into a split-window with <code>Ctrl-a S</code>. <br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/Screen%20Command%20-%20a%20Basic%20Guide/4.jpg"><br>
<br>
You can move between the halves with <code>Ctrl-a TAB</code>. The bottom half is blank for now, and you cannot type in it.<br>
While in the bottom half, use <code>Ctrl-a n</code>to bring up one of the screen sessions we launched earlier. You should now see a bash prompt in each half.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/Screen%20Command%20-%20a%20Basic%20Guide/5.jpg"><br>
<br>
You can now execute separate commands in each half.<br>
<br>
One good use could be to run the space check with a <code>watch</code> command in one half, and your <code>htop</code>, or anything you want to keep an eye on. See the tip below for the watch command example.<br>
<br>
<img src="https://raw.githubusercontent.com/feralhosting/feralfilehosting/master/Feral%20Wiki/Linux%20Command-Line%20-%20Advanced/Screen%20Command%20-%20a%20Basic%20Guide/6.jpg"><br>
<br>
<h2>Tip</h2><br>
<strong>1:</strong> To use the watch command to check your space, just type this command:<br>
<br>
<pre><code> watch -n 60 du ~&#x2F; -s --si</code></pre><br>
It will execute the command you specify, refreshing it on the screen, with an interval of 60 seconds.<br>
<br>
<strong>2:</strong> If you create a <code>.screenrc</code> file in your home directory, you can use the following command in the <code>.screenrc</code> file to create a status bar that will be displayed at the bottom of the screen session (Please see the screenshots above). It will also display a list of active sessions, similar to <code>Ctrl-a w</code>:<br>
<br>
<pre><code># An alternative hardstatus to display a bar at the bottom listing the
# windownames and highlighting the current windowname in blue. (This is only
# enabled if there is no hardstatus setting for your terminal)
hardstatus on
hardstatus alwayslastline
hardstatus string &quot;%{.bW}%-w%{.rW}%n %t%{-}%+w %=%{..G} %H %{..Y} %m&#x2F;%d %C%a &quot;
altscreen on
caption always
caption string &quot;%= %-w%L&gt;%{= BW}%n*%t%{-}%52&lt;%+w %L=&quot;
defscrollback 30000
startup_message off
defsilence on</code></pre><br>
<br>
