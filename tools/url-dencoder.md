---
layout: archive
permalink: /tools/url-dencoder
author_profile: true
redirect_from:
  - /url-dencoder
---

{% include base_path %}
# URL Decoeder/Encoder

<head>
<style type="text/css">
<!--
body {background: white; color: black;}
form {margin: 0;}
h1 {font-family: Arial, sans-serif; line-height: 0.85em; border-bottom: 2px solid;
  margin-bottom: 0.33em; padding-bottom: 0;}

textarea {background: #EEF;}

#footer {border-top: 1px solid #000; color: #999; font: italic 75% sans-serif;}
#footer p {margin: 0 0 1em 0;}
#footer img {float: right; margin: 0 0 0.5em 2em;}
-->
</style>
<script type="text/javascript">
function encode() {
	var obj = document.getElementById('dencoder');
	var unencoded = obj.value;
	obj.value = encodeURIComponent(unencoded).replace(/'/g,"%27").replace(/"/g,"%22");	
}
function decode() {
	var obj = document.getElementById('dencoder');
	var encoded = obj.value;
	obj.value = decodeURIComponent(encoded.replace(/\+/g,  " "));
}
</script>
<style type="text/css">/*
 * contextMenu.js v 1.4.0
 * Author: Sudhanshu Yadav
 * s-yadav.github.com
 * Copyright (c) 2013 Sudhanshu Yadav.
 * Dual licensed under the MIT and GPL licenses
**/

.iw-contextMenu {
    box-shadow: 0px 2px 3px rgba(0, 0, 0, 0.10) !important;
    border: 1px solid #c8c7cc !important;
    border-radius: 11px !important;
    display: none;
    z-index: 1000000132;
    max-width: 300px !important;
    width: auto !important;
}

.dark-mode .iw-contextMenu,
.TnITTtw-dark-mode.iw-contextMenu,
.TnITTtw-dark-mode .iw-contextMenu {
    border-color: #747473 !important;
}

.iw-cm-menu {
    background: #fff !important;
    color: #000 !important;
    margin: 0px !important;
    padding: 0px !important;
    overflow: visible !important;
}

.dark-mode .iw-cm-menu,
.TnITTtw-dark-mode.iw-cm-menu,
.TnITTtw-dark-mode .iw-cm-menu {
    background: #525251 !important;
    color: #FFF !important;
}

.iw-curMenu {
}

.iw-cm-menu li {
    font-family: -apple-system, BlinkMacSystemFont, "Helvetica Neue", Helvetica, Arial, Ubuntu, sans-serif !important;
    list-style: none !important;
    padding: 10px !important;
    padding-right: 20px !important;
    border-bottom: 1px solid #c8c7cc !important;
    font-weight: 400 !important;
    cursor: pointer !important;
    position: relative !important;
    font-size: 14px !important;
    margin: 0 !important;
    line-height: inherit !important;
    border-radius: 0 !important;
    display: block !important;
}

.dark-mode .iw-cm-menu li, .TnITTtw-dark-mode .iw-cm-menu li {
    border-bottom-color: #747473 !important;
}

.iw-cm-menu li:first-child {
    border-top-left-radius: 11px !important;
    border-top-right-radius: 11px !important;
}

.iw-cm-menu li:last-child {
    border-bottom-left-radius: 11px !important;
    border-bottom-right-radius: 11px !important;
    border-bottom: none !important;
}

.iw-mOverlay {
    position: absolute !important;
    width: 100% !important;
    height: 100% !important;
    top: 0px !important;
    left: 0px !important;
    background: #FFF !important;
    opacity: .5 !important;
}

.iw-contextMenu li.iw-mDisable {
    opacity: 0.3 !important;
    cursor: default !important;
}

.iw-mSelected {
    background-color: #F6F6F6 !important;
}

.dark-mode .iw-mSelected, .TnITTtw-dark-mode .iw-mSelected {
    background-color: #676766 !important;
}

.iw-cm-arrow-right {
    width: 0 !important;
    height: 0 !important;
    border-top: 5px solid transparent !important;
    border-bottom: 5px solid transparent !important;
    border-left: 5px solid #000 !important;
    position: absolute !important;
    right: 5px !important;
    top: 50% !important;
    margin-top: -5px !important;
}

.dark-mode .iw-cm-arrow-right, .TnITTtw-dark-mode .iw-cm-arrow-right {
    border-left-color: #FFF !important;
}

.iw-mSelected > .iw-cm-arrow-right {
}

/*context menu css end */</style><style type="text/css">@-webkit-keyframes load4 {
    0%,
    100% {
        box-shadow: 0 -3em 0 0.2em, 2em -2em 0 0em, 3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 -1em, -3em 0 0 -1em, -2em -2em 0 0;
    }
    12.5% {
        box-shadow: 0 -3em 0 0, 2em -2em 0 0.2em, 3em 0 0 0, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 -1em, -3em 0 0 -1em, -2em -2em 0 -1em;
    }
    25% {
        box-shadow: 0 -3em 0 -0.5em, 2em -2em 0 0, 3em 0 0 0.2em, 2em 2em 0 0, 0 3em 0 -1em, -2em 2em 0 -1em, -3em 0 0 -1em, -2em -2em 0 -1em;
    }
    37.5% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em, 3em 0em 0 0, 2em 2em 0 0.2em, 0 3em 0 0em, -2em 2em 0 -1em, -3em 0em 0 -1em, -2em -2em 0 -1em;
    }
    50% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em, 3em 0 0 -1em, 2em 2em 0 0em, 0 3em 0 0.2em, -2em 2em 0 0, -3em 0em 0 -1em, -2em -2em 0 -1em;
    }
    62.5% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em, 3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 0, -2em 2em 0 0.2em, -3em 0 0 0, -2em -2em 0 -1em;
    }
    75% {
        box-shadow: 0em -3em 0 -1em, 2em -2em 0 -1em, 3em 0em 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 0, -3em 0em 0 0.2em, -2em -2em 0 0;
    }
    87.5% {
        box-shadow: 0em -3em 0 0, 2em -2em 0 -1em, 3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 0, -3em 0em 0 0, -2em -2em 0 0.2em;
    }
}

@keyframes load4 {
    0%,
    100% {
        box-shadow: 0 -3em 0 0.2em, 2em -2em 0 0em, 3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 -1em, -3em 0 0 -1em, -2em -2em 0 0;
    }
    12.5% {
        box-shadow: 0 -3em 0 0, 2em -2em 0 0.2em, 3em 0 0 0, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 -1em, -3em 0 0 -1em, -2em -2em 0 -1em;
    }
    25% {
        box-shadow: 0 -3em 0 -0.5em, 2em -2em 0 0, 3em 0 0 0.2em, 2em 2em 0 0, 0 3em 0 -1em, -2em 2em 0 -1em, -3em 0 0 -1em, -2em -2em 0 -1em;
    }
    37.5% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em, 3em 0em 0 0, 2em 2em 0 0.2em, 0 3em 0 0em, -2em 2em 0 -1em, -3em 0em 0 -1em, -2em -2em 0 -1em;
    }
    50% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em, 3em 0 0 -1em, 2em 2em 0 0em, 0 3em 0 0.2em, -2em 2em 0 0, -3em 0em 0 -1em, -2em -2em 0 -1em;
    }
    62.5% {
        box-shadow: 0 -3em 0 -1em, 2em -2em 0 -1em, 3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 0, -2em 2em 0 0.2em, -3em 0 0 0, -2em -2em 0 -1em;
    }
    75% {
        box-shadow: 0em -3em 0 -1em, 2em -2em 0 -1em, 3em 0em 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 0, -3em 0em 0 0.2em, -2em -2em 0 0;
    }
    87.5% {
        box-shadow: 0em -3em 0 0, 2em -2em 0 -1em, 3em 0 0 -1em, 2em 2em 0 -1em, 0 3em 0 -1em, -2em 2em 0 0, -3em 0em 0 0, -2em -2em 0 0.2em;
    }
}</style><style type="text/css">/* This is not a zero-length file! */</style></head>
<body>


<form onsubmit="return false;">
<h1>URL Decoder/Encoder</h1>

<textarea cols="100" rows="20" id="dencoder"></textarea>
<div>
<input type="button" onclick="decode()" value="Decode">
<input type="button" onclick="encode()" value="Encode">
</div>

<ul>
<li>Input a string of text and encode or decode it as you like.</li>
<li>Handy for turning encoded JavaScript URLs from complete gibberish into readable gibberish.</li>
<li>If you'd like to have the URL Decoder/Encoder for offline use, just view source and save to your hard drive.</li>
</ul>

</form>


<div id="footer">
<img alt="Creative Commons License" border="0" src="//creativecommons.org/images/public/somerights.gif">
<p>
<br>
The URL Decoder/Encoder is licensed under a Creative Commons <a href="http://creativecommons.org/licenses/by-sa/2.0/" rel="license">Attribution-ShareAlike 2.0</a> License.
</p>
<p>
This tool is provided without warranty, guarantee, or much in the way of explanation.  Note that use of this tool may or may not crash your browser, lock up your machine, erase your hard drive, or e-mail those naughty pictures you hid in the Utilities folder to your mother.  Don't blame me if anything bad happens to you, because it's actually the aliens' fault.  The code expressed herein is solely that of the author, and he's none too swift with the JavaScript, if you know what we mean, so it's likely to cause giggle fits in anyone who knows what they're doing.  Not a flying toy.  Thank you for playing.  Insert coin to continue.
</p>
</div>



</body></html>
