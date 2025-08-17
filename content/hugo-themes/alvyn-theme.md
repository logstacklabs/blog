+++
date = '2025-08-17T13:48:07+03:00'
draft = false
title = 'Alvyn Theme Configuration'
tags = ['Hugo', 'Web development']
authors = ['msio']
thumbnail = 'images/thumbnail/alvyn.png'
category = 'Hugo Themes'
excerpt = "Alvyn is a clean, minimalist & responsive hugo landing page theme. It's lightweight, built for performance and simplicity, and it supports both dark and light mode."
+++

Alvyn is a clean, minimalist & responsive hugo landing page theme. It's lightweight, built for performance and simplicity, and it supports both dark and light mode. It's SEO friendly and easy to customize.
For more detailed documentation, visit the [**GitHub**](https://github.com/logstacklabs/alvyn.git) repository. And to see the therme demo, visit [logstack.dev](https://logstack.dev).

### 🔧 Installation & Setup
Install the **prerequisites**: Git, dart-sass, and Hugo.

In your site's root directory run the following commands below

```bash
git init
```

```bash
git submodule add https://github.com/logstacklabs/alvyn.git themes/alvyn
```

Or clone the reposirory
```bash
git clone https://github.com/logstacklabs/alvyn.git themes/alvyn
```

Enable the theme in your `hugo.toml`:
```bash
echo "theme = 'alvyn'" >> hugo.toml
```

Install dependencies
```bash
cd themes/alvyn && npm install
```

### Configurations
- Add this configuration to your `hugo.toml` file.

```toml
baseURL = 'https://example.org/'
languageCode = 'en-US'
title = 'Logstack Labs'
theme = 'alvyn'

[params]
    description = ''
    keywords = []

    [params.config]
        logo = ''
        favicon = ''

    [params.config.analytics]
        goatCounter = ''
        googleAnalytics = ''

    [params.config.seo]
        fbAdminsId = ''
        twitterHandle = ''
        opengraphImage = ''
        twitterCardImage = ''

[menus]
    [[menus.main]]
        name = 'About'
        weight = 10
    [[menus.main]]
        name = 'Contact'
        weight = 40
# Add more menus if you want

[outputs]
    home = ['HTML', 'RSS']

[taxonomies]

[minify]
    minifyOutput = false

[module]
    [module.hugoVersion]
        extended = false
        min = '0.148.0'
```

For your sections configurations, create a file `sections.toml` in the `data` directory of your site and add your configurations.
```toml
[hero]
    tagline = ''
    summary = ''
    [[hero.cta]]
        anchor = '' # Link of the CTA button.
        label = '' # Label/Title of the CTA button.
    # A maximum of 3 buttons will be displayed on the hero section


[about]
    title = ''
    summary = ''
    [about.highlights]
        title = ''
        entries = []


[expertise]
    title = ''
    tagline = ''
    [[expertise.entry]]
        icon = ''
        title = ''
        description = ''


[projects]
    title = ''
    tagline = ''
    [[projects.entry]]
        title = ''
        url = ''
        summary = ''
        techStack = []


[rssFeed]
    title = ''
    tagline = ''
    url = ''


[services]
    title = ''
    tagline = ''
    [[services.entry]]
        title = ''
        summary = ''


[team]
    title = ''
    tagline = ''
    [[team.member]]
        avatar = ''
        name = ''
        role = ''
        summary = ''
        [team.member.urls]
            website = ''
            email = ''
            github = ''
            linkedin = ''


[contact]
    title = ''
    tagline = ''
    [contact.forms]
        formSubjects = []
    [contact.forms.keys]
        web3forms = ''
        recaptcha = ''
    [contact.cards]
        title = ''
        phones = []
        hours = []
        emails = []
        locations = []


[footer]
    ccHolder = ''
    [[footer.links]]
        anchor = ''
        label = ''
    [footer.socials]
        GitHub = ''
        youtube = ''
        LinkedIn = ''
    [footer.socials.others]
    # This section is for icons that are not available under font-awesome's `fa-brands` category.
        blog = ''
```
