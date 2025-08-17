+++
date = '2025-08-17T13:48:14+03:00'
draft = false
title = 'Plumeo Theme Configuration'
tags = ['Hugo', 'Web development']
authors = ['msio']
thumbnail = 'images/thumbnail/screenshot.png'
category = 'Hugo Themes'
excerpt = "Plumeo is a clean, lightweight and responsive Hugo theme designed for writers, developers, and creators who want a minimalist, and elegant blog. It's lightweight, supports both dark & light mode, and it's SEO friendly & responsive."
featured = true
+++

Plumeo is a clean, lightweight and responsive **Hugo theme** designed for writers, developers, and creators who want a **minimalist, and elegant blog**. It's lightweight, supports both dark & light mode, SEO friendly and responsive.
For more detailed documentation, visit the [**GitHub**](https://github.com/logstacklabs/plumeo.git) repository. And to see the theme demo, visit [blog.logstack.dev](https://blog.logstack.dev).

### ✨ Features
* 📱 Responsive & mobile-friendly layouts.
* ⚡ Minified assets, lazy-loaded images, google fonts, and assets fingerprinting.
* 📰 Clean & optimized layouts and typography.
* 🏷️ Taxonomy support including categories, tags, and author pages with post counts and icons.
* 📖 Custom render hooks for codeblocks, Images, & blockquotes with 15 different Github styled alerts.
* 🔎 Built-in search functionality.
* 🖼️ Local & Remote image resource handling.
* 📂 SEO friendly (Schema.org markup, Open Graph, Twitter cards, & social meta tags).
* 🔗 Social Share buttons for different social platforms including (Linkedin, Facebook, Mastodon, BlueSky, Threads, WeChat, etc...).
* 🧩 Shortcodes currently has only the contact form & card, more shortcodes will be included in future updates.


### 🛠️ Installation & Setup

Inside your Hugo site's root directory, add as submodule:

```shell
 git init
```

```bash
 git submodule add https://github.com/logstacklabs/plumeo.git themes/plumeo
```

Or clone the repo
```shell
 git clone https://github.com/logstacklabs/plumeo.git themes/plumeo
```

Enable the theme in your `hugo.toml` configuration file
```toml
 theme = 'plumeo'
```

### ⚙️ Configurations

Add these additional configurations to your theme's front matter in the `archetypes/default.md` file
```toml
tags = ['', '']
authors = ['', '']
thumbnail = ''
category = ''
excerpt = ''
```

To enable the search functionality, your `content` directory must containt a `search/_index.md` file.
For static pages that you dont want to list among the list of posts, please add the following configurations to the front matter.
```toml
layout = 'static'
[build]
    render = 'always'
    list = 'never'
```

And for your `hugo.toml` configuration file
```toml { title = hugo.toml }
baseURL = 'https://example.org/'
languageCode = 'en-US'
title = 'Logstack Labs'

# Number of posts you want to display per page
[pagination]
    pagerSize = 10 # Any value you desire
    path = ''

[params]
    tagline = ''
    description = ''
    keywords = []

[menu]
    [[menu.main]]
        name = ''
        url = ''
        weight = 10
        identifier = ''


#####################################################
##*************************************************##
##*************************************************##
##*                                               *##
##*~~~~:    DO NOT EDIT BEYOND THIS POINT    :~~~~*##
##*                                               *##
##*************************************************##
##*************************************************##
#####################################################


[outputs]
    home = ['HTML', 'RSS']
    page = ['HTML', 'RSS']
    rss = ['RSS']
    section = ['HTML', 'RSS']
    taxonomy = ['HTML', 'RSS']
    term = ['HTML', 'RSS']

[mediaTypes]
    [mediaTypes."application/json"]
        suffixes = ["json"]

[outputFormats.JSON]
    mediaType = "application/json"
    isPlainText = true

[taxonomies]
    tag = 'tags'
    author = 'authors'
    category = 'category'

[markup]
    [markup.goldmark]
        [markup.goldmark.parser]
            wrapStandAloneImageWithinParagraph = false
            [markup.goldmark.parser.attribute]
                block = true

[minify]
    minifyOutput = false

enableEmoji = true
enableGitInfo = true
enableRobotsTXT = true
enableFingerprinting = true

[module]
    [module.hugoVersion]
        extended = false
        min = '0.148.0'
```

For the post blog's configurations, create a file `siteconfig.yml` or `siteconfig.toml` in the `data` directory of your site and add the configurations.
```yaml { title = "data/siteconfig.yml" }
# For the site's logo, favicon, & default theme mode
branding:
    theme: ''
    logo: ''
    favicon: ''

# For the site's analytics, and seo
analytics:
    goat_counter: ''
    google_analytics: ''

seo:
    fb_admins_id: ''
    twitter_handle: ''
    opengraph_image: ''
    twitter_card_image: ''

# For the blog posts comment service provider, currently supports Giscus, Utterances, & disqus.
comments:
    isActive: true # Set to true if you want to add comment a service on your posts
    service_provider: '' # Specify comment service priovider [ giscus | disqus | utterances ]
    discus:
        shortname: ''
    utterances:
        repo: ''
        issue_term: ''
        label: ''
        theme: ''
    giscus:
        repo: ''
        repo_id: ''
        category: ''
        category_id: ''
        mapping: ''
        strict: ''
        reactions: ''
        emit_meta: ''
        input_pos: ''
        lang: ''
        theme: ''
        loading: ''

contact:
    card_title: ''
    card_tagline: ''
    form:
        keys:
          web3forms: '' # Web3forms access keys for the contact form
          recaptcha: '' # Not currently available in the current theme version 
        form_subjects:
            - # Subject 1
            - # Subject 2
            - # And so on
    card:
        email: # contact card's email
        phone: # contact card phone number
        address: # contact card's address info

footer:
    copyright_email: ''
    copyright_holder: ''
    links: # Links you want to display on the footer of your site
        - label: # Link 1
          anchor: # https://url1.com/
        - label: # Link 2
          anchor: # https://url2.com/
    socials:
        github: # Social hanles
        linkedin: # Add linkedin handles as in/your_handle or company/company_handle
        others: # For icons not in fontawesome's fa-brands repository
            blog: # entire URL 
```

For the post author/s configurations, create a file `authors.yml` or `authors.toml` in the `data` directory of your site and add the configurations.
Set the keys of each configuration as the author's handle.
```yaml { title = authors.yml }
john: # Author's handle 'john'
    name: '' # Author's Name ie: John Doe
    email: '' #Authors Email ie: john@example.com
    avatar: '' # Authors Avatar Path/Url
    bio: '' # Author's summary/bio
    links:
  #      url: '' # Author's personal website ie: https://johndoe.com
        github: '' # GitHub handle ie: johndoe
        linkedin: '' # LinkedIn handle ie: in/johndoe
```

Add the following configurations in a file named `socialshare.yml` or `socialshare.toml` in the `data` directory, and specify the social share icons you want to add in your blog posts. A maximum of 5 icons including the copy URL icon will be displayed.
Uncomment the social share icon you want to be listed.
```yaml { title = socialshare.yml }
platforms:
    - icon: bluesky
      title: 'Share to BlueSky'
      url: 'https://bsky.app/intent/compose?text={TITLE}%20{URL}'

    - icon: linkedin
      title: 'Share to LinkedIn'
      url: 'https://www.linkedin.com/shareArticle?mini=true&url={URL}&title={TITLE}'

#    - icon: threads
#      title: 'Share to Threads'
#      url: 'https://www.threads.net/intent/post?text={TITLE}%20{URL}'

#    - icon: x
#      title: 'Share to Twitter'
#      url: 'https://twitter.com/intent/tweet?url={URL}&text={TITLE}'

#    - icon: facebook
#      title: 'Share to Facebook'
#      url: 'https://www.facebook.com/sharer/sharer.php?title={TITLE}&u={URL}'


#    - icon: reddit
#      title: 'Share to Reddit'
#      url: 'https://www.reddit.com/submit?url={URL}&title={TITLE}'

#    - icon: whatsapp
#      title: 'Share on WhatsApp'
#      url: 'https://api.whatsapp.com/send?text={TITLE}%20{URL}'

#    - icon: telegram
#      title: 'Share on Telegram'
#      url: 'https://t.me/share/url?url={URL}&text={TITLE}'

#    - icon: envelope
#      title: 'Share to Email'
#      url: 'mailto:?subject={TITLE}&body={TITLE}%0A{URL}'

#    - icon: pinterest
#      title: 'Share to Pinterest'
#      url: 'https://pinterest.com/pin/create/button/?url={URL}&description={TITLE}'

#    - icon: hacker-news
#      title: 'Share to Hacker News'
#      url: 'https://news.ycombinator.com/submitlink?u={URL}&t={TITLE}'

#    - icon: flipboard
#      title: 'Share on Flipboard'
#      url: 'https://share.flipboard.com/bookmarklet/popout?v=2&title={TITLE}&url={URL}'

#    - icon: tumblr
#      title: 'Share on Tumblr'
#      url: 'https://www.tumblr.com/widgets/share/tool?canonicalUrl={URL}&title={TITLE}'

#    - icon: buffer
#      title: 'Share to Buffer'
#      url: 'https://buffer.com/add?url={URL}&text={TITLE}'

    - icon: weibo
      title: 'Share to Weibo'
      url: 'https://service.weibo.com/share/share.php?url={URL}&title={TITLE}'
```
#### SEE: [the blog](https://blog.logstack.dev/plumeo-theme) for all the configurations:

- To work on Plumeo locally:
```shell
 hugo server
```

- To build your hugo site
```shell
 hugo
```

- Preview your site at [localhost:1313](http://localhost:1313).

- To update, run the following commands:
```shell
 cd themes/plumeo
```

```shell
 git pull origin main
``` 

```shell
 cd ../..
```

```shell
 git submodule update --remote --rebase
```
