
<h1 align="center">
AcadHomepage
</h1>

<div align="center">

[![](https://img.shields.io/github/stars/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io)
[![](https://img.shields.io/github/forks/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io)
[![](https://img.shields.io/github/issues/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io)
[![](https://img.shields.io/github/license/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io/blob/main/LICENSE)  | [中文文档](./docs/README-zh.md) 
</div>

<p align="center">A Modern and Responsive Academic Personal Homepage</p>

<p align="center">
    <br>
    <img src="docs/screenshot.png" width="100%"/>
    <br>
</p>

Some examples:
- [Demo Page](https://rayeren.github.io/acad-homepage.github.io/)
- [Personal Homepage of the author](https://rayeren.github.io/)

## Key Features
- **Automatically update google scholar citations**: using the google scholar crawler and github action, this REPO can update the author citations and publication citations automatically.
- **Support Google analytics**: you can trace the traffics of your homepage by easy configuration.
- **Responsive**: this homepage automatically adjust for different screen sizes and viewports.
- **Beautiful and Simple Design**: this homepage is beautiful and simple, which is very suitable for academic personal homepage.
- **SEO**: search Engine Optimization (SEO) helps search engines find the information you publish on your homepage easily, then rank it against similar websites.

## Quick Start

1. Fork this REPO and rename to `USERNAME.github.io`, where `USERNAME` is your github USERNAME.
1. Configure the google scholar citation crawler:
    1. Find your google scholar ID in the url of your google scholar page (e.g., https://scholar.google.com/citations?user=SCHOLAR_ID), where `SCHOLAR_ID` is your google scholar ID.
    1. Set GOOGLE_SCHOLAR_ID variable to your google scholar ID in `Settings -> Secrets -> Actions -> New repository secret` of the REPO website with `name=GOOGLE_SCHOLAR_ID` and `value=SCHOLAR_ID`.
    1. Click the `Action` of the REPO website and enable the workflows by clicking *"I understand my workflows, go ahead and enable them"*. This github action will generate google scholar citation stats data `gs_data.json` in `google-scholar-stats` branch of your REPO. When you update your main branch, this action will be triggered. This action will also be trigger 08:00 UTC everyday.
1. Generate favicon using [favicon-generator](https://redketchup.io/favicon-generator) and download all generated files to `REPO/images`.
1. Modify the configuration of your homepage `_config.yml`:
    1. `title`: the title of your homepage
    1. `description`: the description of your homepage
    1. `repository`: USER_NAME/REPO_NAME  
    1. `google_analytics_id` (optional): google analytics ID
    1. SEO Related keys (optional): get these keys from search engine consoles (e.g. Google, Bing and Baidu) and paste here.
    1. `author`: the author information of this homepage, including some other websites, emails, city and univeristy.
    1. More configuration details are described in the comments.
1. Add your homepage content in `_pages/about.md`.
    1. You can use html+markdown syntax just same as jekyll.
    1. You can use a `<span>` tag with class `show_paper_citations` and attribute `data` to display the citations of your paper. Set the data to the google scholar paper ID. For
        ```html
        <span class='show_paper_citations' data='DhtAFkwAAAAJ:ALROH1vI_8AC'></span>
        ``` 
        > Q: How to get the google scholar paper ID?   
        > A: Enter your google scholar homepage and click the paper name. Then you can see the paper ID from `citation_for_view=XXXX`, where `XXXX` is the required paper ID.
1. Your page will be published at `https://USERNAME.github.io`.

## Debug Locally

1. Clone your REPO to local using `git clone`.
1. Install Jekyll building environment, including `Ruby`, `RubyGems`, `GCC` and `Make` following [the installation guide](https://jekyllrb.com/docs/installation/#requirements).
1. Run `bash run_server.sh` to start Jekyll livereload server.
1. Open http://127.0.0.1:4000 in your browser.
1. If you change the source code of the website, the livereload server will automatically refresh.
1. When you finish the modification of your homepage, `commit` your changings and `push` to your remote REPO using `git` command.

# Acknowledges

- AcadHomepage incorporates Font Awesome, which is distributed under the terms of the SIL OFL 1.1 and MIT License.
- AcadHomepage is influenced by the github repo [mmistakes/minimal-mistakes](https://github.com/mmistakes/minimal-mistakes), which is distributed under the MIT License.
- AcadHomepage is influenced by the github repo [academicpages/academicpages.github.io](https://github.com/academicpages/academicpages.github.io), which is distributed under the MIT License.

```
Wenjun-Ji.io
├─ Gemfile
├─ Gemfile.lock
├─ LICENSE
├─ README.md
├─ _config.yml
├─ _data
│  └─ navigation.yml
├─ _includes
│  ├─ analytics.html
│  ├─ author-profile.html
│  ├─ browser-upgrade.html
│  ├─ fetch_google_scholar_stats.html
│  ├─ head
│  │  └─ custom.html
│  ├─ head.html
│  ├─ masthead.html
│  ├─ scripts.html
│  ├─ seo.html
│  └─ sidebar.html
├─ _layouts
│  └─ default.html
├─ _pages
│  └─ about.md
├─ _sass
│  ├─ _animations.scss
│  ├─ _archive.scss
│  ├─ _base.scss
│  ├─ _buttons.scss
│  ├─ _footer.scss
│  ├─ _forms.scss
│  ├─ _masthead.scss
│  ├─ _mixins.scss
│  ├─ _navigation.scss
│  ├─ _notices.scss
│  ├─ _page.scss
│  ├─ _print.scss
│  ├─ _reset.scss
│  ├─ _sidebar.scss
│  ├─ _syntax.scss
│  ├─ _tables.scss
│  ├─ _utilities.scss
│  ├─ _variables.scss
│  └─ vendor
│     ├─ breakpoint
│     │  ├─ _breakpoint.scss
│     │  ├─ _context.scss
│     │  ├─ _helpers.scss
│     │  ├─ _legacy-settings.scss
│     │  ├─ _no-query.scss
│     │  ├─ _parsers.scss
│     │  ├─ _respond-to.scss
│     │  ├─ _settings.scss
│     │  └─ parsers
│     │     ├─ _double.scss
│     │     ├─ _query.scss
│     │     ├─ _resolution.scss
│     │     ├─ _single.scss
│     │     ├─ _triple.scss
│     │     ├─ double
│     │     │  ├─ _default-pair.scss
│     │     │  ├─ _default.scss
│     │     │  └─ _double-string.scss
│     │     ├─ resolution
│     │     │  └─ _resolution.scss
│     │     ├─ single
│     │     │  └─ _default.scss
│     │     └─ triple
│     │        └─ _default.scss
│     ├─ font-awesome
│     │  ├─ _animated.scss
│     │  ├─ _bordered-pulled.scss
│     │  ├─ _core.scss
│     │  ├─ _fixed-width.scss
│     │  ├─ _icons.scss
│     │  ├─ _larger.scss
│     │  ├─ _list.scss
│     │  ├─ _mixins.scss
│     │  ├─ _rotated-flipped.scss
│     │  ├─ _screen-reader.scss
│     │  ├─ _shims.scss
│     │  ├─ _stacked.scss
│     │  ├─ _variables.scss
│     │  ├─ brands.scss
│     │  ├─ fontawesome.scss
│     │  ├─ regular.scss
│     │  ├─ solid.scss
│     │  └─ v4-shims.scss
│     ├─ magnific-popup
│     │  ├─ _magnific-popup.scss
│     │  └─ _settings.scss
│     └─ susy
│        ├─ _su.scss
│        ├─ _susy.scss
│        ├─ _susyone.scss
│        └─ susy
│           ├─ _su.scss
│           ├─ language
│           │  ├─ _susy.scss
│           │  ├─ _susyone.scss
│           │  ├─ susy
│           │  │  ├─ _background.scss
│           │  │  ├─ _bleed.scss
│           │  │  ├─ _box-sizing.scss
│           │  │  ├─ _breakpoint-plugin.scss
│           │  │  ├─ _container.scss
│           │  │  ├─ _context.scss
│           │  │  ├─ _gallery.scss
│           │  │  ├─ _grids.scss
│           │  │  ├─ _gutters.scss
│           │  │  ├─ _isolate.scss
│           │  │  ├─ _margins.scss
│           │  │  ├─ _padding.scss
│           │  │  ├─ _rows.scss
│           │  │  ├─ _settings.scss
│           │  │  ├─ _span.scss
│           │  │  └─ _validation.scss
│           │  └─ susyone
│           │     ├─ _background.scss
│           │     ├─ _functions.scss
│           │     ├─ _grid.scss
│           │     ├─ _isolation.scss
│           │     ├─ _margin.scss
│           │     ├─ _media.scss
│           │     ├─ _padding.scss
│           │     └─ _settings.scss
│           ├─ output
│           │  ├─ _float.scss
│           │  ├─ _shared.scss
│           │  ├─ _support.scss
│           │  ├─ float
│           │  │  ├─ _container.scss
│           │  │  ├─ _end.scss
│           │  │  ├─ _isolate.scss
│           │  │  └─ _span.scss
│           │  ├─ shared
│           │  │  ├─ _background.scss
│           │  │  ├─ _container.scss
│           │  │  ├─ _direction.scss
│           │  │  ├─ _inspect.scss
│           │  │  ├─ _margins.scss
│           │  │  ├─ _output.scss
│           │  │  └─ _padding.scss
│           │  └─ support
│           │     ├─ _background.scss
│           │     ├─ _box-sizing.scss
│           │     ├─ _clearfix.scss
│           │     ├─ _prefix.scss
│           │     ├─ _rem.scss
│           │     └─ _support.scss
│           └─ su
│              ├─ _grid.scss
│              ├─ _settings.scss
│              ├─ _utilities.scss
│              └─ _validation.scss
├─ assets
│  ├─ css
│  │  ├─ academicons.css
│  │  ├─ academicons.min.css
│  │  ├─ collapse.css
│  │  └─ main.scss
│  ├─ fonts
│  │  ├─ academicons.eot
│  │  ├─ academicons.svg
│  │  ├─ academicons.ttf
│  │  ├─ academicons.woff
│  │  ├─ fa-brands-400.eot
│  │  ├─ fa-brands-400.svg
│  │  ├─ fa-brands-400.ttf
│  │  ├─ fa-brands-400.woff
│  │  ├─ fa-brands-400.woff2
│  │  ├─ fa-regular-400.eot
│  │  ├─ fa-regular-400.svg
│  │  ├─ fa-regular-400.ttf
│  │  ├─ fa-regular-400.woff
│  │  ├─ fa-regular-400.woff2
│  │  ├─ fa-solid-900.eot
│  │  ├─ fa-solid-900.svg
│  │  ├─ fa-solid-900.ttf
│  │  ├─ fa-solid-900.woff
│  │  └─ fa-solid-900.woff2
│  └─ js
│     ├─ _main.js
│     ├─ collapse.js
│     ├─ main.min.js
│     ├─ plugins
│     │  ├─ jquery.fitvids.js
│     │  ├─ jquery.greedy-navigation.js
│     │  ├─ jquery.magnific-popup.js
│     │  ├─ jquery.smooth-scroll.min.js
│     │  └─ stickyfill.min.js
│     └─ vendor
│        └─ jquery
│           └─ jquery-1.12.4.min.js
├─ docs
│  ├─ README-zh.md
│  └─ screenshot.png
├─ google_scholar_crawler
│  ├─ main.py
│  └─ requirements.txt
├─ images
│  ├─ 500x300.png
│  ├─ AngleRoCL.png
│  ├─ android-chrome-192x192.png
│  ├─ android-chrome-512x512.png
│  ├─ apple-touch-icon.png
│  ├─ birefnet.png
│  ├─ chatnku.png
│  ├─ dayspark.png
│  ├─ favicon-16x16.png
│  ├─ favicon-32x32.png
│  ├─ favicon.ico
│  ├─ myself.jpg
│  ├─ restartuniversity.png
│  ├─ site.webmanifest
│  └─ wave_and_wave.png
└─ run_server.sh

```