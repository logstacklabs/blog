+++
date = '2025-08-14T22:53:58+03:00'
title = 'Uniport Theme Configuration'
tags = ['Hugo', 'Web development']
authors = ['msio']
thumbnail = 'https://blog.msio.me/assets/resources/uniport-hugo-theme/thumbnail.webp'
category = 'Hugo Themes'
excerpt = "Uniport-H is a clean, responsive, one-paged, and lightweight customizable portfolio theme built for Hugo. The theme is easy to customize, It also comes as a GitHub template so it's easy to install & use. The design is partly inspired by Brian Yu's Website"
draft = false
+++

Uniport-H is a clean, responsive, one-paged, and lightweight customizable portfolio theme built for Hugo. The theme is easy to customize, It also comes as a GitHub template so it's easy to install & use. The design is partly inspired by Brian Yu's Website.
See the following link for the demo [uniport-h.msio.me](https://uniport-h.msio.me/).

### Installation & Setup

1. Install the prerequisites:
   - Git
   - Hugo _(minimum v0.148.0)_

2. This theme is available as a template.
   - Click on the `Use this template` button and then select `Create a new repository`.
   - Name the new repository with a name of your choice.
   - Clone the repository then modify to your satisfaction.

3. If you don't want to use the template you can follow the steps below:
   - In your site's root directory run the following commands below
```sh
 git init
```

```sh
 git submodule add https://github.com/logstacklabs/plumeo.git themes/plumeo
```

Or clone the repository
```shell
git clone https://github.com/logstacklabs/plumeo.git themes/plumeo
```

Enable the theme in your `hugo.toml` configuration file
```shell
 echo "theme = 'uniport-h'" >> hugo.toml
```

### Configurations
After completing any of the steps above add the configurations below to your `hugo.toml` file in your site's root directory.

```toml
baseURL = '' # Replace with your domain
languageCode = '' # Example: en-US, tr-TR...etc.
title = '' # Replace with the title of your site

theme = 'uniport-h'

# NOTE:
#   Values must be provided to the following parameters before running your site
#   - FirstName, LastName, Skills, JobTitle, SiteDescription and Profile Summary.
# ----------------------------------------------------------------------------------------
# The default site title is written as "First Name | Job Title"
# If you want to use custom site title with the title parameter above
# then change the value of the parameter 'defaultTitle' to true.
[params]
    defaultTitle = false
    firstName = ''
    lastName = ''
    skills = []
    description = ''

    [params.job]
        title = ''
        company = ''

    [params.education]
        title = ''
        institution = ''

[params.profile]
    greetings = 'Hello!' # Or whatever you prefer
    summary = []
    email = ''
    resume = ''

[params.rssFeed]
# If you have a blog that you want to embed to your site
# Specify the RSS feed url of your blog (ie: https://blog.com/feed.xml)
# The 3 most recent post from your site will be displayed.
    Url = ''

[params.socials]
# Place your entire social url as shown below.
    GitHub = 'your_handle'
    LinkedIn = 'in/your_handle'
# If you don't want to display a social icon, delete the parameter or leave it empty ''
# If you want to add more social links to it, makesure the icons are available in the fontawesome fa-brands icon repository.
    BlueSky = 'your_handle'
    Instagram = 'your_handle'
    [params.socials.others]
    # This section is for icons that are not available under `fa-brands` category.
        Code = 'img/brand.png'
        blog = 'img/brand.png'

[params.footer]
# Name to show in the copyright message
    ccName = ''
    ccEmail = ''
# Displays: ©️${CurrentYear}, ${ccName}. Some Rights Reserved

# Replace the id below with your google analytics measurement ID and goatcounter ID
[params.analytics]
    GoatCounter = ''
    GoogleAnaltics = ''

[params.config]
    theme = ''
    logo = ''
    avatar = ''
    favicon = ''

[params.config.analytics]
    goatCounter = ''
    googleAnalytics = ''

[params.config.seo]
    fbAdminsId = ''
    twitterHandle = ''
    opengraphImage = ''
    twitterCardImage = ''

# Do not edit beyond this line
[outputs]
    home = ['HTML', 'RSS']

[minify]
    minifyOutput = false

enableRobotsTXT = true
enableFingerprinting = true

[taxonomies]

[module]
    [module.hugoVersion]
        extended = false
        min = '0.148.0'
```

- To work on Plumeo locally:
```shell
 hugo server
```
- To build your hugo site
```shell
 hugo
```

Preview your site locally at [localhost:1313](http://localhost:1313).

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

See the [**GitHub**](https://github.com/logstacklabs/uniport-h.git) repository for more detailed documentation.
