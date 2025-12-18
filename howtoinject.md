This is just a simple script to enject it into the console
on pony.town go to your console and network and block the request url for the bootstrap.js and reload the site
go to your console and allow pasting
paste in the code below and press enter


```javscript
  console.log("Injecting")
  const INJECT_URL = "https://raw.githubusercontent.com/meowseal/deobfuscated-ponytown-bootstrapjs/refs/heads/main/bootstrap.js";
  
  async function inject(url) {
      if (!url) return;
  
      const response = await fetch(url);
      const code = await response.text();
  
      const script = document.createElement("script");
      script.textContent = code;
  
      document.body.appendChild(script);
  }
  
  inject(INJECT_URL);


```
