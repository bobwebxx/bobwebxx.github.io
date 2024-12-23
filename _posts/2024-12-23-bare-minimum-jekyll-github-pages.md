---
layout: default
title:  "Bare Minimum to install Jekyll Github Pages"
tags: meta
---

# Absolute Bare Minimum to install Jekyll Github Pages

Least amount of code required to start install Jekyll Github Pages.

All you need to do is add `_config.yaml` and it will build.

I added the following at it rendered:
`_config.yaml`

```
title: Bob's blog
email: bobwebxx@gmail.com
description: >- # this means to ignore newlines until "baseurl:"
  Bob's blog
baseurl: "" # the subpath of your site, e.g. /blog
url: "https://bobwebxx.github.io"
github_username:  bobwebxx
remote_theme: pages-themes/minimal@v0.2.0
markdown: kramdown
plugins:
  - jekyll-feed
  - jekyll-remote-theme
```

Obviously a bunch of this is optional but this is still very light.

---

Writing some quick posts. Choosing to upgrade to github-pages themes. They are maintained here: https://github.com/pages-themes/

I choose minimal: https://pages-themes.github.io/minimal/

Syntax can just be: 

```
theme: jekyll-theme-minimal
```

This just worked.

But per the above is more fancy. Feels more pro-bro, probably just aliases and no differences of substance though.

---



