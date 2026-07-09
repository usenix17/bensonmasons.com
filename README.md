# Benson Masons, a [Hugo](https://gohugo.io/) powered site for the Mercer Lodge No. 290.

The intent of this code base is to provide a solid Hugo site with basic features and include best practices for performance, accessibility, and rapid development.

![Dev Benson Masons Screenshot](https://github.com/sashakarcz/bensonmasons.com/blob/a6c70f3b00d6d49bdc493fb15c8bc53033ddddf2/static/images/dev.bensonmasons.com_.png)

[Live Site](https://bensonmasons.com/)

Features

- Responsive
- Accessible
- Contact form
- Paypal integration
- Google Calendar integration


## Continuous Building and Deploying

When a change is committed to `main`, the site is built and deployed automatically by the [GitHub Actions workflow](.github/workflows/hugo.yml) using [GitHub Pages](https://pages.github.com/).

## Installation

### Local Development

> ⚠️ If you installed a [Hugo binary](https://gohugo.io/getting-started/installing/#binary-cross-platform), you may not have Go installed on your machine. To check if Go is installed:
> ```
> $ go version
> ```
>  Go modules were considered production ready in v1.14. [Download Go](https://golang.org/dl/).

1. Check out this repo:

   ```
   $ git clone https://github.com/sashakarcz/bensonmasons.com.git
   ```

1. Change directories into the git repo and launch hugo:

   ```bash
   $ cd bensonmasons.com && hugo serve
   ```
   Example output will be like:

```shell
Start building sites … 
hugo v0.124.0+extended linux/amd64 BuildDate=unknow

                   | EN   
-------------------+------
  Pages            |  20  
  Paginator pages  |   0  
  Non-page files   |   1  
  Static files     | 799  
  Processed images |   0  
  Aliases          |   1  
  Cleaned          |   0  

Built in 4146 ms
Environment: "development"
Serving pages from disk
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1) 
Press Ctrl+C to stop

```

Navigate to http://127.0.0.1:1313, and the site should be locally rendered.


#### Paths of note

  - Take a look inside the [`content`](https://github.com/sashakarcz/bensonmasons.com/tree/main/content/) directory of this site for all pages.
  - [`static/images`](https://github.com/sashakarcz/bensonmasons.com/tree/main/static/images) is where all photos should go.
  - [`hugo.toml`](https://github.com/sashakarcz/bensonmasons.com/blob/main/hugo.toml) contains all the metadata, site settings, social media links, and logo.

#### Activate the contact form

We use [formspree.io](//formspree.io/) as proxy to send the emails to the Lodge. Each month, visitors can send us up to one thousand emails without incurring extra charges. Visit the Formspree site to get the "action" link and add it to your shortcode like this:

```
{{< form-contact action="https://formspree.io/f/xgegvojz"  >}}
```

#### Social Follow + Share

The theme automatically adds "Follow" link icons to the header and footer and "Share" link icons to pages unless `disable_share` parameter is set to true either on the site level (site params) or page level (front matter). Each built-in services sports a label, an icon and a color. We have Facebook and Instagram currently configured in the `hugo.toml` file:

```toml
[[params.ananke_socials]]
name = "facebook"
url = "https://www.facebook.com/mercermasoniclodge"

[[params.ananke_socials]]
name = "instagram"
url = "https://www.instagram.com/mercerlodge290"
```

### Adding a new page
Add a new page to the local git repo in the [`content`](https://github.com/sashakarcz/bensonmasons.com/tree/main/content/) directory. Best practice would be to copy an existing page / directory. For example,

```bash
tree content
content
├── about
│   └── index.md
├── calendar
│   └── index.md
├── contact-us
│   └── index.md
├── dues
│   └── index.md
├── hall-rental
│   └── index.md
├── _index.md
├── officers
│   └── index.md
├── the-patron-saints-and-the-point-within-a-circle
│   └── index.md
└── updates
    ├── _index.md
    ├── notables
    │   └── index.md
    └── upcoming-public-events
        └── index.md
```

Let's copy the about directory and name it foo:

```bash
cp -r content/about content/foo
```

Now the structure looks like:

```bash
tree content
content
├── about
│   └── index.md
├── calendar
│   └── index.md
├── contact-us
│   └── index.md
├── dues
│   └── index.md
├──foo
│   └── index.md
├── hall-rental
│   └── index.md
├── _index.md
├── officers
│   └── index.md
├── the-patron-saints-and-the-point-within-a-circle
│   └── index.md
└── updates
    ├── _index.md
    ├── notables
    │   └── index.md
    └── upcoming-public-events
        └── index.md
```

Now we can edit the `content/foo/index.md` file:

```bash
---
title: "New Title"   <-- This is the title, and what will be shown in the menu if the menu section is added
menu:                <-- This will add the page to the menu
  main:              <-- This is the main menu
    weight: 2        <-- This is the ordering from left to right. A weight of 1 will make it the left most item.
---

# New Heading

## New Sub-heading
```

Please reference [Hugo's docs](https://gohugo.io/content-management/organization/) for more detail.
