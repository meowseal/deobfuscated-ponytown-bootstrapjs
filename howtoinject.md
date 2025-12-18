This is just a simple script to enject it into the console
we can use tampermonkey to inject JS scripts onto sites


```javscript
    // ==UserScript==
    // @name         Pony Town bootstrap override
    // @match        https://pony.town/*
    // @run-at       document-start
    // @grant        GM_xmlhttpRequest
    // ==/UserScript==
    
    GM_xmlhttpRequest({
      method: "GET",
      url: "https://raw.githubusercontent.com/meowseal/deobfuscated-ponytown-bootstrapjs/refs/heads/main/bootstrap-734e029ae3.js",
      onload(res) {
        // Monkey-patch before page code runs
        eval(res.responseText); // allowed in userscript sandbox
      }
    });

```
