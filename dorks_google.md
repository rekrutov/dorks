
### operator
     ""    -   strict search             
    \*     -   any text                  
     .     -   any symbol                
    \-     -   exclude word              
    \..    -   range                     
     |     -   logical OR                
     ()    -   group miltiple searches   

### keys word
    define:      - search for the definition of a word or phrase
    cache:       - find the most recent cache of a webpage
    filetype:    - search for particular types ( pdf, log, ... )
    site:        - search for result from a particular website
    related:     - search for sites related to a given domain
    intitle:     - search for pages with a particular word in the title tag
    allintitle:  - all in title (multiple)
    inurl:       - serch for pages with a particular word in URL
    allinurl:    - all in URL (multiple)
    intext:      - search for pages with a word in their content
    allintext:   - all word in page content (multiple)
    weather:     - search for the weather in a location
    stocks:      - search for stock information for a ticker
    map:         - force google to show map result 
    movie:       - search for information about a movie 
    in:          - convert one unit to another
    course:      - search for result from a particular source in Google News
    before:      - search for result from before a particular source in Google News ( yyyy-mm-dd )
    after:       - search for result from after a particular date ( yyyy-mm-dd )

### use  
    1. Footholds - web-shell, public file manager 
    (intitle:«phpshell» OR intitle:«c99shell» OR intitle:«r57shell» OR intitle:«PHP Shell » OR intitle:«phpRemoteView») `rwx` «uname»

    2. Files containing usernames - log file, ... 
    filetype:reg reg +intext:«internet account manager»

    3. Senstive Directories - directories with various information (personal documents, vpn configs, hidden repositories, etc.)
    «Config» intitle:«Index of» intext:vpn
     (intext:«index of /.git») («parent directory»)

    4. Web server detection - version or any information about web-server 
    inurl:»/web-console/» 
    intitle:«Administration Console»

    5. Vulnerable files - scripts containing known vulnerabilities
    allinurl:forcedownload.php?file=

    6. Vulnerable Servers - installation scripts, web shells, open administrative consoles, ...
    intitle:phpMyAdmin «Welcome to phpMyAdmin ***» «running on * as root@*»

    7. Error messages - various errors and warnings often reveal important information - from the CMS version to passwords
    «Warning: mysql_query()» «invalid query»

    8. Files containing juicy info - certificates, backups, emails, logs, sql scripts, ...
    filetype:sql and «insert into» -site:github.com

    9. Files containing password - anything that may contain passwords – logs, SQL scripts, ...
    filetype:log intext:password | pass | pw
    ext:sql intext:username intext:password

    10. Sensitive Online Shopping info - info about online shoping
    dcid= bn= pin code=

    11. Netword or vulnerabillity data - info that is not directly related to the web resource, but affects the network or other non-web services
    inurl:proxy | inurl:wpad ext:pac | ext:dat findproxyforurl

    12. Pages containing login portals - pages containing login forms
    intext:«2016 SAP AG. All rights reserved.» intitle:«Logon»

    13. Various Online Devices - Printers, routers, monitoring systems, ...
    intitle:»hp laserjet» inurl:SSI/Auth/set_config_deviceinfo.htm

    14. Advisories and Vulnerabilities - sites on vulnerable CMS versions
    inurl:fckeditor -intext:«ConfigIsEnabled = False» intext:ConfigIsEnabled

