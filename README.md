Visit our website: [goyobot.github.io](https://goyobot.github.io).



## About this repo

This site is built on [Jekyll](https://jekyllrb.com). It generates a *static* website from the source code, so the load time is blazingly fast.

Every time you push something to the `master` branch, GitHub runs Jekyll on that commit and re-builds the static site (it may take some seconds).

Keep the source code in English, please.



## Authors info

How authors (members) are managed:

- The folder `_authors` contains a file per author. Use the `default.md` template.
- Your `<author>.md` file 
- Authors are set as a collection in `_config.yml`, and they are set as `output: true` so that a page is created for them. The default layout for authors is configured as `layout: user_profile`.
- The link to your author is `authors/<author>` by default, but the `permalink: <author>` in your markdown file can be used to make the link be simply `/<author>`.

Make sure yout `team` in yout markdown file is set to one of the team ids in `_data/teams.yml`.

Store your icon file as `assets/img/authors/<author>.png`. It should be 200x200 px.


## Local development

Before pushing something to the public repo, you should test it locally.

1. Install [Jekyll](https://jekyllrb.com) following the instructions.
2. Clone this repo.
3. Build and start a local server to view your site:

```bash
$ cd goyobot.github.io
$ jekyll serve
```

Now, open `http://localhost:4000` in a browser _et voilà_.

The moment you edit and save a source code file while Jekyll is serving, it rebuilds the file to `site`, so it's very fast for testing.

For more in-depth info about Jekyll, you can use [this tutorial](https://santi-gf.github.io/jekyll) (in Spanish).
