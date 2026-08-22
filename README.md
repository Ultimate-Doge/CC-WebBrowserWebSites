# RedWeb Website Registry

This repository hosts websites for the RedWeb browser in GlasspaneOS.

## Required GitHub Pages setting

Open the repository on GitHub, choose **Settings**, then **Pages**. Under
**Build and deployment**, choose **Deploy from a branch**, select `main` and
`/(root)`, then save.

## Registering a domain

Add an entry to `registry.json`. The normal RedWeb ending is `.rb`.

```json
"example.rb": {
  "name": "Example Website",
  "description": "My website",
  "manifest": "https://ultimate-doge.github.io/CC-WebBrowserWebSites/sites/example/redweb.json"
}
```

Create the matching website folder under `sites/`. Every website needs a
`redweb.json` manifest and an HTML homepage.

RedWeb currently supports safe simple HTML: `<h1>`, `<h2>`, `<h3>`, `<p>`,
`<br>` and `<a href="...">`. Scripts and styles are removed. App-download
tags are recognised, but app installation remains disabled until the safety
confirmation system is complete.
