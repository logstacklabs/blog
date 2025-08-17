+++
date = '2025-08-17T13:06:26+03:00'
draft = false
title = 'Muxel Theme Configuration'

tags = ['Hugo', 'Web development']
authors = ['msio']
thumbnail = 'images/thumbnail/muxel.png'
category = 'Hugo Themes'
excerpt = "Muxel is a modern, clean & responsive tech-themed Hugo portfolio theme designed for developers, and professionals who want to showcase their work with style and clarity. It's built for performance and simplicity, and it offers a light-first design (with dark mode support coming soon), and responsive layouts."
+++

Muxel is a modern, clean & responsive tech-themed Hugo portfolio theme designed for developers, and professionals who want to showcase their work with style and clarity. It's built for performance and simplicity, and it offers a light-first design (with dark mode support coming soon), and responsive layouts.

For more detailed documentation, visit the [**GitHub**](https://github.com/logstacklabs/muxel.git) repository. And to see the therme demo, visit [msio.me](https://msio.me).

### Installation & Setup

1. Install the **Prerequisites**: `Git`, `dart-sass`, & `Hugo`.

- In your site's root directory, run:
```shell
 git init
```

- Add the theme as git submodule:
```bash
 git submodule add https://github.com/logstacklabs/muxel.git themes/muxel
```

OR clone the repository
```shell
 git clone https://github.com/logstacklabs/muxel.git themes/muxel
```

- Install the dependencies
```bash
 cd themes/muxel && npm install && cd ../..
```

- Enable the theme in your `hugo.toml` configuration file
```bash
 echo "theme = 'muxel'" >> hugo.toml
```

- To preview the site locally run:
```bash
 hugo server
```
then visit [localhost:1313](http://localhost:1313).

### Configuration
- Add this configuration to your `hugo.toml` file.
```toml
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = ''
theme = 'muxel'

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
        name = 'Resume'
        weight = 20
    [[menus.main]]
        name = 'Portfolio'
        weight = 30
    [[menus.main]]
        name = 'Services'
        weight = 40
    [[menus.main]]
        name = 'Contact'
        weight = 50


# Do not edit beyond thie point
[outputs]
    home = ['HTML', 'RSS']

enableGitInfo = true
enableRobotsTXT = true
enableFingerprinting = true

[taxonomies]

[minify]
    minifyOutput = true

[module]
    [module.hugoVersion]
        extended = false
        min = '0.148.0'

```

For you portfolio summary, create a file `summary.toml` in the `data` directory of your site and add the configurations.
```toml
[bio]
# Name, Summary, CTA buttons, and array of taglines to show on the hero section.
    fullName = ''
    summary = ''
    taglines = []
    [[bio.cta]]
        anchor = '' # Link of the CTA button.
        label = ''  # Label/Title of th CTA button.
    [[bio.cta]]
        anchor = ''
        label = ''
        download = true # Supposed you link a CV, set whether the file is downloadable or not (false by default).

[about]
# Section Title, Professional Photo, & bio/summary of your professional portfolio.
    sectionTitle = 'About Me'
    tagline = ''
    avatar = ''
    summary = []
```

For the resume section of your portfolio, create a file `resume.toml` in the `data` directory of your site and add the configurations.
```toml
sectionTitle = '' # Example: "My Resume"
# Contains 3 sections (Work Experience, Education, & Certifications)
# Each section requires subsection Title, & array of work/education/certification information including
# Roles/Degree/Certificates, duration/dates, company/school name & logo, brief job/education description...etc.
[experience]
    subSectionTitle = '' # Example: "Work Experience"
    [[experience.entry]]
        role = ''
        duration = ''
        companyName = ''
        companyLogo = ''
        summary = ''

[education]
    subSectionTitle = ''
    [[education.entry]]
        title = ''
        date = ''
        schoolLogo = ''
        schoolName = ''
        summary = ''

[certificates]
    subSectionTitle = ''
    [[certificates.entry]]
        title = ''
        issuer = ''
        dateIssued = ''
        validationUrl = ''
        summary = ''

```

For the projects, skills, services, and testimonials section of your site, create a file `portfolio.toml` in the `data` directory of your site and add the configurations.
```toml
sectionTitle = '' # Example: "My Portfolio"
[projects]
    subSectionTitle = '' #Example: "Recent Projects"
    [[projects.entry]]
        title = ''
        demoUrl = ''
        repoUrl = ''
        screenshot = ''
        techStack = []
        summary = ''

[skillset]
    subSectionTitle = ''
    [[skillset.entry]]
        icon = '' #icon can either be an emoji or a font-awesome icon.
        title = ''
        summary = ''

[services]
    subSectionTitle = ''
    [[services.entry]]
        icon = ''
        title = ''
        summary = ''

[testimonials]
    subSectionTitle = ''
    [[testimonials.entry]]
        name = ''
        title = ''
        avatar = ''
        testimonial = ''

```

For the contact section of your portfolio, create a file `contact.toml` in the `data` directory of your site and add the configurations.
```toml
[forms]
    sectionTitle = ''
    sectionTagline = ''
    formSubjects = [] # A dropdown list of subjects to add to the contact form
    [forms.keys]
        web3forms = '' # Visit `https://web3forms.com/` for an access key
        recaptcha = '' # Google recaptcha-V3 (Will be available in future versions).

[card]
    title = '' # Title of the contact card
    email = ''
    phone = ''
    address = ''

# When adding social URL's, makesure the icon is available on fontawesome and makesure to set the icon name as the key of the social link as shown below.
[socialAccounts]
    GitHub = ''
    BlueSky = ''
    LinkedIn = '' #eg: in/handle or company/handle
    Instagram = ''
    [socialAccounts.others]
    # This section is for icons that are not available under `fa-brands` category.
        blog = ''
```

- To update the theme, run the following commands:
```shell
 cd themes/muxel
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
