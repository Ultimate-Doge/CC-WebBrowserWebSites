# Making a RedWeb Website

This guide is for beginners. You do not need to know Lua, own a server, or use
Rednet. RedWeb websites use small HTML files hosted through GitHub Pages.

## What you need

- A GitHub account.
- A text editor, such as Notepad or GlassCode.
- A name for your website.
- A fake RedWeb address ending in `.rb`, such as `mygame.rb`.

## The three parts of a website

Every website needs:

1. A folder inside `sites`.
2. A `redweb.json` manifest describing the website.
3. An `index.html` file containing the homepage.

The central `registry.json` file connects the fake `.rb` address to the
website manifest.

## Step 1: Copy the template

Copy the `website-template` folder and place the copy inside `sites`.
Rename the copied folder using a short name without spaces.

Example:

```text
sites/
└── mygame/
    ├── redweb.json
    └── index.html
```

Use lowercase letters, numbers, hyphens, or underscores for the folder name.

## Step 2: Edit redweb.json

Open `redweb.json` and change its values:

```json
{
  "redwebVersion": 1,
  "name": "My Game Website",
  "author": "Your Name",
  "description": "News and downloads for my game",
  "homepage": "index.html"
}
```

Important rules:

- Keep quotation marks around text.
- Keep commas at the end of every line except the final setting.
- Keep `redwebVersion` set to `1`.
- The homepage should normally be `index.html`.

## Step 3: Make the homepage

Open `index.html` and replace its contents. Here is a complete example:

```html
<h1>My Game Website</h1>
<p>Welcome to my RedWeb website!</p>

<h2>About the game</h2>
<p>This is where I can describe my game.</p>

<a href="about.html">Read more</a>
<a href="redweb.rb">Return to the RedWeb homepage</a>
```

## Supported HTML

RedWeb intentionally supports a small and safe set of HTML.

| Code | Purpose |
|---|---|
| `<h1>Title</h1>` | Large page heading |
| `<h2>Heading</h2>` | Section heading |
| `<h3>Heading</h3>` | Smaller heading |
| `<p>Text</p>` | Paragraph |
| `<br>` | New line |
| `<a href="page.html">Open page</a>` | Link to another page |
| `<a href="other.rb">Open site</a>` | Link to another RedWeb website |

CSS, JavaScript, videos, forms, and normal browser extensions are not
supported. Script and style tags are removed for safety.

## Step 4: Add another page

Create another HTML file in the same website folder:

```text
sites/
└── mygame/
    ├── redweb.json
    ├── index.html
    └── about.html
```

Example `about.html`:

```html
<h1>About My Game</h1>
<p>I started making this game in 2026.</p>
<a href="index.html">Back to the homepage</a>
```

## Step 5: Choose a fake address

Choose an unused address ending in `.rb`, such as `mygame.rb`. Ask the owner
of the RedWeb registry to add it to `registry.json`.

The entry should look like this:

```json
"mygame.rb": {
  "name": "My Game Website",
  "description": "News and downloads for my game",
  "manifest": "https://ultimate-doge.github.io/CC-WebBrowserWebSites/sites/mygame/redweb.json"
}
```

There must be a comma between entries. A complete registry looks like:

```json
{
  "registryVersion": 1,
  "domains": {
    "welcome.rb": {
      "name": "Welcome to RedWeb",
      "description": "The first RedWeb website",
      "manifest": "https://ultimate-doge.github.io/CC-WebBrowserWebSites/sites/welcome/redweb.json"
    },
    "mygame.rb": {
      "name": "My Game Website",
      "description": "News and downloads for my game",
      "manifest": "https://ultimate-doge.github.io/CC-WebBrowserWebSites/sites/mygame/redweb.json"
    }
  }
}
```

## Step 6: Submit the website

The easiest beginner method is:

1. Put `redweb.json`, `index.html`, and any extra HTML pages in one folder.
2. Name the folder after the website.
3. Send that folder and the requested `.rb` address to the registry owner.
4. The owner checks the files and uploads them under `sites`.
5. The owner adds the address to `registry.json`.

Experienced GitHub users can fork the repository, add their folder and
registry entry, then open a pull request.

## Step 7: Wait for GitHub Pages

GitHub Pages may take a few minutes to update. Restart RedWeb after the files
are live. The new site should then appear on `redweb.rb`.

## Website addresses

- Typing `mygame` opens `mygame.rb`.
- Typing `mygame.com` also tries `mygame.rb`.
- Links between pages may use names such as `about.html`.
- Links to other sites should use their complete fake address, such as
  `news.rb`.

## App downloads

RedWeb recognises the planned `app-download` tag, but installing apps from
websites is not enabled yet. Do not advertise a working app download until
the permission and safety screen has been completed.

## Common problems

### Website not found

Check that the address exists in `registry.json` and ends in `.rb`.

### Invalid website

Check `redweb.json` for missing quotation marks, commas, or brackets.

### Page not found

Check spelling and capitalisation. `About.html` and `about.html` can be
different names on GitHub Pages.

### Changes do not appear

Wait a few minutes for GitHub Pages, then close and reopen RedWeb.

### Text is cut off

Use shorter paragraphs and add headings or extra pages. Use the mouse wheel
to scroll down longer pages.

## Safety rules

- Never place passwords, API secrets, private keys, or personal information
  inside website files.
- Do not attempt to hide executable Lua inside a website.
- Do not impersonate another website or person.
- Only download apps from authors you trust once downloads are supported.
- Registry owners should inspect submissions before publishing them.
