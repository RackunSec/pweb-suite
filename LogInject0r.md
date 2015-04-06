LogInject0r - code injection tool for web server logs (LFi Attack)

_**About**_

This tool searches out the log file for the web server that hosts the LFi vulnerability and clones the /etc directory on the system locally by injection PHP exec() functions in the log itself.

_**Depends**_

use LWP::UserAgent (Perl)
use Term::ANSIColor (Perl)

_**Manual**_

Usage: ./LogInject0r -u < URL >

_**Demo**_

<a href='http://weaknetlabs.com/pcrack/pcrack.mp4'>MP4 Video Demo of "pCrack" (pWeb) Suite showing off LogInject0r</a>

_**Author(s)**_

Trevelyn weaknetlabs[-at-]gmail

_**TODO / Future**_