# xssPlay XSS Automation Tool #

**xssPlay** is an automation tool for finding and exploiting non-persistent XSS vulnerabilities in web applications and dynamic pages. This tool will actually mechanize screenshots, using the MozRepl firefox plugin, of the defaced webpage (if successful and specified) in the background while it tests each GET parameter in the passed URL.

The URL specified after '-u' **must** contain a filename and GET parameters for xssPlay to work. It does do recursion and can crawl through the file specified (e.g. index.php?foo=bar,filename.aspx?foo=bar&bar=baz,events.asp?bar=foo) for links and will test each link.

<a href='http://www.youtube.com/watch?v=VPuJM7H5AC8'>YouTube Video Example</a>

This tool is valuable not only to the penetration tester, but to the web programmer as well for testing code. It has the ability to detect and defeat magic quotes for defacement, detect input sanitation code, and even detect custom built search bars.

<a href='http://weaknetlabs.com/images/xssplay0.png'>Full sized screenshot of xssPlay and its ability to take screenshots in WEAKERTH4N Linux</a>

To learn more about XSS vulnerabilities in depth, please read "aCross the Internet Oceans - Cross Site Scripting for Internet Sailors" by Douglas Berdeaux on <a href='http://weaknetlabs.com/AcrosstheInternetSeas.pdf'>WeakNetLabs.com</a>

## Dependencies (4 Perl modules/1 Firefox plugin) ##
<a href='http://search.cpan.org/~gaas/libwww-perl-6.04/lib/LWP.pm'>LWP;</a>
<a href='http://search.cpan.org/~gaas/libwww-perl-6.04/lib/LWP/UserAgent.pm'>LWP::UserAgent;</a>
<a href='http://search.cpan.org/~rra/Term-ANSIColor-3.02/ANSIColor.pm'>Term::ANSIColor;</a>
<a href='http://search.cpan.org/~corion/WWW-Mechanize-Firefox-0.66/lib/WWW/Mechanize/Firefox.pm'>WWW::Mechanize::Firefox;</a>

<a href='https://addons.mozilla.org/en-us/firefox/addon/mozrepl/'>Firefox MozRepl Plugin</a>

## Manual ##
./xssPlay -u URL (options)

### Options ###
**-s** (for screenshots)

**-i** (specify img url to deface with)

**-c** (use only CSS to deface web application)

**-a** (m|s|x|string) (specify user agent to use, or choose random)

**-o** (html|txt) (specify log output type)

**-r** (recursive for crawling)

m = mobile,
s = standard,
x = choose randomly for each http request,
string = make it anything you want!

**Important:** Before starting xssPlay you need to open Firefox and start the MozRepl plugin and leave the browser open.

`Tools->MozRepl->Start `

## User Agents ##
You can now randomly choose user agents to specify them statically. Simply specify `-u m` for random mobile user agent, or `-u s` for a random standard desktop user agent. Warning: this will fill your pentest lab or victim's HTTP server log(s) with falsified information.

Note: For user agents to be random and work correctly, the file ../includes/user\_agent\_list.txt needs to be accessible by xssPlay. This file comes with the latest version of the pWeb Suite.

### Agents ###
Mobile: iPhone, iPad, Opera Mini, Blackberry and Android<br />
Standard: Chrome, Firefox, Internet Explorer, Lynx and Netscape.

### Examples ###
```
root@wt4:/pwnt/www/pWeb/XSS# ./xssPlay -a m -i 'http://127.0.0.1/vuln/xssplay.png' -s -u 'http://127.0.0.1/vuln/xss.php?foo=foo&bar=bar&baz=baz&title=lulz'

  xssPlay - XSS Vulnerability Finder Tool.
  coded by Douglas WeakNetLabs@Gmail.com

 [ * ] Randomly choosing Mobile user agent
 [ * ] Using user agent: Opera/9.80 (BlackBerry; Opera Mini/6.24209/27.1366; U; en) Presto/2.8.119 Version/11.10
root@wt4:/pwnt/www/pWeb/XSS# ./xssPlay -a m -i 'http://127.0.0.1/vuln/xssplay.png' -s -u 'http://127.0.0.1/vuln/xss.php?foo=foo&bar=bar&baz=baz&title=lulz'

  xssPlay - XSS Vulnerability Finder Tool.
  coded by Douglas WeakNetLabs@Gmail.com

 [ * ] Randomly choosing Mobile user agent
 [ * ] Using user agent: Mozilla/5.0 (BlackBerry; U; BlackBerry 9800; en-US) AppleWebKit/534.8+ (KHTML, like Gecko) Version/6.0.0.448 Mobile Safari/534.8+
root@wt4:/pwnt/www/pWeb/XSS# ./xssPlay -a s -i 'http://127.0.0.1/vuln/xssplay.png' -s -u 'http://127.0.0.1/vuln/xss.php?foo=foo&bar=bar&baz=baz&title=lulz'

  xssPlay - XSS Vulnerability Finder Tool.
  coded by Douglas WeakNetLabs@Gmail.com

 [ * ] Randomly choosing PC user agent
 [ * ] Using user agent: Mozilla/4.8 [en] (WinNT; U)
root@wt4:/pwnt/www/pWeb/XSS# ./xssPlay -a s -i 'http://127.0.0.1/vuln/xssplay.png' -s -u 'http://127.0.0.1/vuln/xss.php?foo=foo&bar=bar&baz=baz&title=lulz'

  xssPlay - XSS Vulnerability Finder Tool.
  coded by Douglas WeakNetLabs@Gmail.com

 [ * ] Randomly choosing PC user agent
 [ * ] Using user agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_6_8) AppleWebKit/535.7 (KHTML, like Gecko) Chrome/16.0.912.36 Safari/535.7
root@wt4:/pwnt/www/pWeb/XSS# ./xssPlay -a s -i 'http://127.0.0.1/vuln/xssplay.png' -s -u 'http://127.0.0.1/vuln/xss.php?foo=foo&bar=bar&baz=baz&title=lulz'

  xssPlay - XSS Vulnerability Finder Tool.
  coded by Douglas WeakNetLabs@Gmail.com

 [ * ] Randomly choosing PC user agent
 [ * ] Using user agent: Mozilla/5.0 (Windows; U; Windows NT 5.0; fr-FR; rv:0.9.4) Gecko/20011128 Netscape6/6.2.1
root@wt4:/pwnt/www/pWeb/XSS#
```

## logs ##
Not only does xssPlay take screenshot, but it has the ability to log all activity. When xssPlay is started and it finds that the specified domain host is up and accessible, it creates a directory with the domain name. e.g. say we specify 'http://127.0.0.1/vuln/xss.php?id=foo&bar=blah', xssPlay will create the directory '127.0.0.1' to put the screenshots and log file into.

The log file has the following structure:
`[timestamp] [url return vulnerable]: URL`

## TODO ##