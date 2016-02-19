# pweb-suite
This Suite (formerly known as the "pCrack Suite") of tools is used primarily or web application vulnerability testing. This is an older project that began around May of 2011 and comes with every version of Weakerthan Linux starting at 4. 

# Tools Listing
<table>
  <tr><td>CMS - WP_Sniper</td><td>Wordpress vulnerability testing</td></tr>
  <tr><td>File Inclusion - HelLFiRE</td><td>LFI vulnerability testing</td></tr>
  <tr><td>File Inclusion - LogInject0r</td><td>LFi - log injection exploit</td></tr>
  <tr><td>Mathematics - Fibonacci</td><td>Calculates Fibonacci sequence with just two variables</td></tr>
  <tr><td>Mathematics - Primes</td><td>Pprime numbers generator</td></tr>
  <tr><td>(OSINT) Online Resources - Havijmd5BF</td><td>Havij Report file finder (Uses Google)</td></tr>
  <tr><td>(OSINT) Online Resources - md5online</td><td>MD5 Rainbow table lookup</td></tr>
  <tr><td>(OSINT) Online Resources - pBincracker</td><td>Pastebin passwords search</td></tr>
  <tr><td>(OSINT) Online Resources - ripemd160online</td><td>RIPEMD160 Rainbow table lookup</td></tr>
  <tr><td>(OSINT) Online Resources - sha1online</td><td>SHA1 Rainbow table lookup</td></tr>
  <tr><td>(OSINT) Online Resources - sha1on256ine</td><td>SHA256 Rainbow table lookup</td></tr>
  <tr><td>Recon - FileScope</td><td>File and Directory brute force tool</td></tr>
  <tr><td>Recon - STGB</td><td>SImple plain text Google Browser</td></tr>
  <tr><td>SQL Injection - SMSQLi</td><td>Simple MySQL Injector</td></tr>
  <tr><td>Password Cracking - EtsyShadow</td><td>Cracking password from recovered /etc/shadow- file</td></tr>
  <tr><td>Word List Generation - RePsychoLoop</td><td>permutation generator using word lists or characters</td></tr>
  <tr><td>XSS - XSSPlay!</td><td>Cross Site Scripting vulnerability testing and graphical automation</td></tr>
  <tr><td>XSS - StringEnc</td><td>Obfuscation generator for XSS or Code Injection attacks</td></tr>
</table>
# Screenshots
xssPlay! Screenshots (links open in new tab):<br />
<a target="_blank" href="https://weaknetlabs.com/images/xssplay0.png"><img src="https://weaknetlabs.com/images/xssplay0.png" width="500"/></a><br />
<a target="_blank" href="https://weaknetlabs.com/images/xssplayscreen0.png"><img src="https://weaknetlabs.com/images/xssplayscreen0.png" width="500"/></a><br />

# YouTube Video Demos
xssPlay! (<a href="https://www.youtube.com/watch?v=VPuJM7H5AC8">https://www.youtube.com/watch?v=VPuJM7H5AC8</a>)<br />
Misc, MySQLi, etc (<a href="https://www.youtube.com/watch?v=clY6A_mXn4g">https://www.youtube.com/watch?v=clY6A_mXn4g</a>)

# Usage
All tools come with a Help dialog, simply run the tool with ./tool --help for more information on how to use it.

# Perl Dependencies
LWP; LWP::UserAgent; Term::ANSIColor; WWW::Mechanize::Firefox;LWP; Term::ANSIColor; Digest::MD5; Crypt::PasswdMD5
Firefox MozRepl Plugin (<a href="https://addons.mozilla.org/en-US/firefox/addon/mozrepl/">https://addons.mozilla.org/en-US/firefox/addon/mozrepl/</a>);<br /><br />
These can be installed using CPAN from the terminal, e.g. "cpan -i Term::ANSIColor" or, if using Linux, from your package management system.

# Thank you

                          |          |
                          |\         |\
                          ||\        ||\
                          |||\       |||\
                          ||||\      ||||\       |,
                          |||||\     |||||\      |\
                          ||||||\    ||||||\     ||\
              ____        |||||||\   |||||||\    |||\
             '--O_]       |-------   |-------    ||||\
       '-----...'- '----. |\         |           |----`
              \=========--'-,________|___________|\_         
               \===========--|_|_|_|_|_|_|_|=======/
              . \===========------------===="WNL"=/
            '  .~~'~,.=======-----------------===/
     ~~~~~~~~~~  ~ ~~ ~`~~~~~~~~~~~~~~~~~~~~~~~~'~~~~~~~~~~~
 Thank you for sailing WeakNet Laboratories...
