---
title: Understanding the basics
subtitle: Comprehensive guide to installing, utilizing, and customizing the Knowledge Base Hugo theme available for purchase on ThemeForest.
date: 2023-05-26
lastmod: 2023-06-01
author: ravikanth
menu:
  docs:
    weight: 3
    parent: Week 1
---

## Setup
### Installation and development

Install [Hugo](https://gohugo.io/installation/).

Install dependencies:
`npm install`

To start developing: 
`npm run dev`

To get out of developing mode you need to do **Ctrl+c** twice.


## Basic theme setup

### Site URL
Set the base hostname and protocol for your site in `config.yml` file: 

```yaml
baseURL: "https://my-site.com"
```

### Update favicon
You can find the current favicons inside the `/static/images/` directory, just replace it with your new favicons.

### Update logo
The theme uses two logo files one larger for desktop and one smaller mark logo for mobile. If you don't intend to use mark logo, set the same logo file for both.

Add your logo image files to `/static/images/` directory, then specify the logo files in `config.yml`:

```yaml
params:
  logo: "/images/logo-main.svg"
  logo_mark: "/images/logo-mark.svg"
```

### Navigation menus
Theme uses four default Hugo menus, these can be set in `config.yml` under relevant language:
- Navbar 
- Footer
- Social
- Docs

Docs menu is used for the documentation sidebar, set the parent items in `config.yml`:
```yaml
languages:
  en:
    menu:
      docs:
      - name: Introduction
        weight: 10
        pre: square-3-stack-3d #optional icon from https://heroicons.com/
        params:
          description: Sint ipsa praesentium dolor error cumque velit tenetur quaerat exercitationem conse.
      - name: Tutorials
        weight: 20
        pre: academic-cap
        params:
          description: Sint ipsa praesentium dolor error cumque velit tenetur quaerat exercitationem conse.
```

Next set child menu items in docs posts front matter:
```yaml
menu:
  docs:
    weight: 20
    parent: Introduction
```

### Analytics
Theme support Google analytics and [Fathom analytics](https://usefathom.com/), enable by setting ID in `config.yml`:
```yaml
params:
  analytics_fathom: ANALYTICS_ID
  analytics_google: ANALYTICS_ID
```

## Content

### Authors
Set author in post front matter, reference author `username` from `data/authors.yml`:
```yaml
author: joshua
```

Add authors in `data/authors.yml`:
```yaml
- username: joshua
  name: Joshua Birdman
  image: images/joshua.jpg
```

### Blocks

Theme uses blocks layout as source of content for pages. The blocks layout and contents are defined in page front matter. Set the page layout to `layout: blocks`. Available blocks: `cards, contact-form, contact-info, cta, faq, navigation`.

Example CTA block:
```yml
blocks:
- block: cta
  heading: Ready to get started?
  copy: Morbi eget neque vel turpis lacinia eget neque vel turpis lacinia lacinia eget neque.
  icon: thin-rocket
  button:
    text: Get started
    url: "#"
```

All block demos are included in the theme pages.

### Icons
Some blocks have options to display icons, the icons are located in `layouts/partials/icons/` folder, when specifying icons in block reference only the icon file name without the `.svg` extension.

### Contact form
Contact form is setup and ready to use with [Netlify](https://www.netlify.com/) hosting.

### Post content

For general markdown syntax see [Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

### Image shortcode
Upload images to `/assets/images/` folder and use this shortcode to add it in content:

{&lbrace;< image src="images/abstract-1.jpg" alt="Lorem" >&rbrace;}

## Customization

### String translation

Set your default language code in `config.yml`:
```yml
defaultContentLanguage: "en"
```
Theme strings can be translated in `i18n/en.yml`, duplicate the current English translation `en.yml` file, then replace `en` with your new language code.

```yml
name:
  other: "Name"
email:
  other: "Email"
```

### Code highlighter style
Set the style in `config.yml`:
```yml
markup:
  highlight:
    style: nord
```
List of available styles can be found [here](https://xyproto.github.io/splash/docs/all.html).

### Page blocks
New site blocks can be added in `layouts/partials/blocks/` directory.

### Brand colors
Theme uses TailwindCSS default colors:
```txt
text-sky-500
text-sky-600
bg-sky-500
bg-sky-600
bg-sky-700
```

Search and replace the colors or modify sky colors in `tailwind.config.js`:
```js
theme: {
  extend: {
    colors: {
      sky: {
        500: '#0ea5e9',
        600: '#0284c7',
        700: '#1d4ed8',
      }
    }
  }
}
```

## Support
Customer support is provided through our Envato item support tab for up to six months from the purchase date and is provided Monday to Friday during the business week. We aim to answer all support requests daily, most are handled within 24h.

Please note items downloaded from Envato Elements are not supported so you will be unable to get assistance with technical questions, installation, third-party assets or direct guidance.

Before contacting support please:

- Read this documentation
- Describe your problem in detail
- Include links
- Attach screenshot