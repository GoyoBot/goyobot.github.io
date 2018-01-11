Visit our website: [goyobot.github.io](https://goyobot.github.io).



## About this repo

This site is built on [Jekyll](https://jekyllrb.com). It generates a *static* website from the source code, so the load time is blazingly fast.

Every time you push something to the `master` branch, GitHub runs Jekyll on that commit and re-builds the static site (it may take some seconds).

Keep the source code in English, please.



## Member info

If you are a new member, please add your personal information:

- `_data/members.yml` keeps the main organizational structure. Make sure you have a name there and the organization is correct. Keep a simple name there; it is only used as a reference.
- Given your internal name in the previous step, add a file like `_data/<member>.yml`.
- `_data/default.yml` has the default data if your user info file is missing. Use it as a template.

Store your icon file in `assets/img/members/<member>.png`.


## Local development

Before pushing something to the public repo, you should test it locally.

1. Install [Jekyll](https://jekyllrb.com) following the instructions.
2. Clone this repo.
3. Build and start a local server to view your site:

    $ cd goyobot.github.io
    $ jekyll serve

Now, open a browser in `localhost:4000` to check your changes _et voilà_.

The moment you edit and save a source code file while Jekyll is serving, it rebuilds the file to `site`, so it's very fast for testing.

For more in-depth info about Jekyll, you can use [this tutorial](https://santi-gf.github.io/jekyll) (in Spanish).
