# ![][php-info-logo-8] Pretty PHPinfo tool



## Purposes

This [one page](info.php) admin tool was created to help manage several virtual hosting plans with different settings of PHP.

This tool can be easily embedded into any PHP-driven CMS, which in fact was done by me in some projects.

For easy reading and comparing settings on different hosting was done:

### 2002-2008

- single PHP file
- visual sectioning
- section navigation pane
- PHP 4 support
- easy reading colors in 2 stylesheet with embedded base64 graphics
- visual differences when comparing settings on 2 different hostings by using color schemes; see [screenshots](screenshots/)
- NO javascript
- NO frames, nor iFrames
- additional non-standard info
- no credits and module descriptions, just technical info by key-value

### 2013

- PHP5 OOP - compact file, easy and safe reuse of PHPinfo code, PHP4 support was gone as unneccessary
- LESS sources for stylesheets
- 2 ready to use PHP files with different stylesheets embedded
- styles optimized for Chrome and Firefox on tablets
- dropped MySQL info and other non-standard info

> to use with PHP4 take a look at [`info-2008.php`](dev/info-2008.php) in [`dev`](dev/) folder

### 2016

- stylesheets combined to single LESS to easy switch style by changing `class` of `BODY` or any another container
- JS added by following reasons: 
	
	1. optimization for browsers I'm use, 
	2. possibility to quick change of a look, including FavIcon, 
	3. possibility to quick modify the data at client side with DevTools
	4. quick search/filters - as modern UI\UX trends: I've become old and lazy, I want to press only key, but don't scroll :)
	5. remember choosed color scheme in browser, not at hosting
	6. just ONE file to deploy

- no 3d party JS libraries are used
- dropped support for IE < 10
- dropped CSS hacks

## Installation

Just copy `info.php` to your virtual hosting by FTP or any another way into directory wich can be reachable by http access.

> **NOTE** check permissions of directory: 

	1) on *NIX hosting file must be written with `644` permissions at least
	2) php scripts must be allowed to be launched in this directory (check `.htaccess` files)
	3) directory must be under DOCUMET_ROOT

Strongly recommended to place this file in restricted area of your site or delete them when it become unneccessary: 
PHP info gives large amount system info, which can be used 3d persons to bring lot of hedache to you and lot of destruction to your site.

Also, you can run folowing code inside desired directory of server:

```bash
wget https://raw.githubusercontent.com/SynCap/PHP-Info/master/info.php
```


## Known issues

### FavIcon not supported in IE

Because they do not support PNG icons properly, 
and I don't use IE in everyday task. I see no reasons to prepare and embed `ICO` files. 
Icons in this tools taken from the PNG logos wich (only 2 images) are embedded into CSS.


### Some lacks in old and mobile browsers

Current version did not tested with IE < 11, and any other browsers published before December 2015.

This version is not intended to use through devices with small screens (less than 1024 pixels 
in horizontal dimension and less than 500 px in vertical).

### No subheaders in some tables

Yes, I know. When I'll need it, I'll fix this. If you really need it - modify code at line where comments marked `** RE:`
where Regular Expressions are reside. You may want to catch `tr` with `class="h"` to determine the subheader.

Check line marked `** Table row:`, where new tables are builts.

### Only 2 columns of 3-column tables is retrived

Are you really need it? If so, modify code if regular expressions at line where comments marked `** RE:`.
You may need to catch all 3 values, and at neext close line marked `2016:`, they can be added to array which keep all gathered values.

Check line marked `** Table row:`, where new tables are builts.

## TODOs

* by now I see no neccessary to distribute this tool through Composer's Packagist or any other package distribution net, but if I'll see enough requests to do so, I'll do it. 100 request - is not enought, but 1 - can be, if need very-very much…

## Non evident things you have to know to maximize effeciency of this tool

Last changes brings some lazy life features:

- No need to select `INFO_ALL` in native mode request select box, just click GO button in form, or hit the `Enter`, when form is focused

- Going to native PHP info pages through top menu select goes like modern drop down menus does - just select desired mode and if execution of Javasript is enabled in your browser, request will be fired

- Pressing `Esc` will clear filter box and restore visibility of all sections and corresponding navigation items. No matter which part of page is focused.

- In most cases only pair of key's hits needed to bring desired section into viewport. To get find exact value - use browser builin serch functionality, usually just hit `Ctrl+F`. Using two level serching is much productive.

- Fork this project and get the tool of your needs. Placing of non-minimized version of JS into `inof.php` lets you advantages of control the look of data through the browser's developing tools. I.e. you can change contents of view just inplace. Some example of this you can find in source of `dev/info.js`, modify it as you need at any time in modern browsers, don't waste time to check every value line by line, char by char. Hm, but when you get the result of native phpinfo, just `Ctrl+F` can help to you…
	
## License

Distribution granted with MIT [license](LICENSE)

[php-info-logo-8]:dev/img/g1.png