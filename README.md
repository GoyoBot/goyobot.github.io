Visit our website: [goyobot.github.io](https://goyobot.github.io).


## About this repo

This site is built on [Jekyll](https://jekyllrb.com). It generates a *static* website from the source code, so the load time is blazingly fast.

Every time you push something to the `master` branch, GitHub runs Jekyll on that commit and re-builds the static site (it may take some seconds).

Keep the source code in English, please.



## Basic Jekyll

- `_config.yml` is the main config file for the site.
- Your posts go in `_posts/`.
- See the whole [directory structure](https://jekyllrb.com/docs/structure/).

Any post or page has two parts [explained here](https://jekyllrb.com/docs/posts/):

- [Front Matter written in YAML](https://jekyllrb.com/docs/frontmatter/).
- Body written in Markdown.

```
---
# Start always with three dashes (no intros before!)
# This part is written in YAML
---
This part is written in Markdown
```

Example of post: `_posts/2018-01-15-Basic-file.md`:

```
---
# The layout variable tells Jekyll to use the
# layout template in _layout/.
# You need it unless you have a default one set in _config.yml
layout: default

# The layout typically uses some variables set here such as:
title: Basic file
author: santi
date: 2018-01-15
---

The contents of my post/page.
```


## Our templates

The templates we use can be found in `_layouts` and `_includes`.

We use [Bootstrap 4](https://v4-alpha.getbootstrap.com) and [Font Awesome](http://fontawesome.io).

Since Jekyll uses [Kramdown](https://kramdown.gettalong.org/syntax.html) as a Markdown renderer, it's very easy to add Bootstrap classes:

```markdown
**Well done!** You successfully read [this alert message](#){:.alert-link}.
{:.alert .alert-success}

<!-- Instead of -->

<div class="alert alert-success" role="alert">
  <strong>Well done!</strong> You successfully read <a href="#" class="alert-link">this alert message</a>.
</div>
```


## Authors info

How authors (members) are managed:

- `_authors/` contains a file per author.
- Add your `<author>.md` file if you don't have one using `default.md` as a template.
- The link to your author is `goyobot.github.io/authors/<author>` by default, but the `permalink: <author>` in your markdown file can be used to make the link be simply `goyobot.github.io/<author>`.
- Make sure yout `team` in your markdown file is set to one of the team ids in `_data/teams.yml`.
- Store your icon file as `assets/img/authors/<author>.png` (200x200 px).

Example of `<author>.md`:

```
---
# Set your link name. If empty, the default is /authors/<user>
permalink: myname

# Info for the page layout
# The team must be an id from _data/teams.yml
team: smr
shortname: Miembro
fullname: Este personaje es un misterio...
website: http://goyobot.github.io
github: goyobot
twitter: goyobot
icon: assets/img/authors/default.png
---

This is the author description that will appear in his page.

- Use markdown syntax here
- Actually, Jekyll uses [kramdown](https://kramdown.gettalong.org), so you have some fancy tricks{:badge badge-primary}.
- No need to write a real, formal, boring bio zzz...
```


**Info:** This way of handling authors is not the default in Jekyll ([more info](https://www.siteleaf.com/blog/author-pages-in-jekyll-and-siteleaf/)). It is configured in `_config.yml` as:

```yaml
collections:
  authors:       # Set the _authors directory as a collection
    output: true # Make the author profile public

defaults:
  # Set the default layout for all authors
  - scope:
      path: _authors
    values:
      layout: user_profile
```



## Local development

Before pushing something to the public repo, you should test it locally.

1. Install [Jekyll](https://jekyllrb.com) following the instructions.
2. Clone this repo.
3. Build and start a local server to view your site:

```bash
$ git clone https://github.com/GoyoBot/goyobot.github.io.git
$ cd goyobot.github.io
$ rake serve
```

Now, open `http://localhost:4000` in a browser _et voilà_.

The moment you edit and save a source code file while Jekyll is serving, it rebuilds the file to `_site`, so it's very fast for testing.

For more in-depth info about Jekyll, you can use [this tutorial](https://santi-gf.github.io/jekyll) (in Spanish).



## Advanced dev

Use `bundler` to install all dependencies found in `Gemfile`:

```bash
$ gem install bundler  # If not installed
$ bundler install
```

A `Rakefile` is provided to simplify some tasks:

```bash
$ rake
rake build  # Build the jekyll site
rake serve  # Build and serve the jekyll site
rake test   # Build and test the jekyll site
```

Use `rake test` to test the whole website with [HTML-Proofer](https://github.com/gjtorikian/html-proofer) (broken links and images, bad HTML...)
