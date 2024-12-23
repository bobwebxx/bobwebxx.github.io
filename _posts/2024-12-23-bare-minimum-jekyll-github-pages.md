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

Final bare minimum tree:

```
├── _config.yml
├── _layouts
│   └── default.html
└── _posts
    └── 2024-12-23-blah.md

```

Can add `404.html` in root if care. But this seems to be the absolute least required by github-pages.

If you want to actually see your posts in some sort of nav you have to modify `defaults.html` per below.

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

### To add "posts" (blog/navigation)

Minimum required:

Required programmatically:

root directory:

* `_posts`

Everything in that directory **must have**

* naming syntax: **`YYYY-MM-DD-blah.md`**
* "front matter"

**Naming syntax:**

`YYYY-MM-DD-blah.md`

The `YYYY-MM-DD` is business critical to Jekyll for rendering and display. If the date is in the future, it won't show until the future.

https://jekyllrb.com/docs/posts/

**Front Matter**

There's a bunch of built-in variables that can be used, but this is the bare minimum to render:
```
---
layout: default
title:  "Bare Minimum to install Jekyll Github Pages"
---
```

https://jekyllrb.com/docs/front-matter/

ngl, I don't love ruby: https://github.com/jekyll/jekyll/blob/master/lib/jekyll/frontmatter_defaults.rb

#### Navigation

To list posts the following can then be added to a template `_layouts/default.html`:

```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
```

That's per the docs. I'm more minimalist than that myself though.
