# rs-content

[GitLab Stage Deploy](https://stage-gitlab.rework-space.com)

## Useful links

- [Hugo documentation](https://gohugo.io/documentation)
- Base theme - [Ananke](https://github.com/theNewDynamic/gohugo-theme-ananke)
- [Hugo docker images](https://hub.docker.com/r/klakegg/hugo)
- [Hugo Internal Templates](https://github.com/gohugoio/hugo/tree/master/tpl/tplimpl/embedded/templates)
- [Hugo themes](https://themes.gohugo.io/)
- [Tachyons documentation](http://tachyons.io/docs/)
- [Tachyons color codes](https://tachyons.io/docs/themes/skins/) for base theme
- Blogpost - [Image processing using hugo](https://clavinjune.dev/en/blogs/image-processing-using-hugo/)
- Blogpost - [Multilingual](https://www.regisphilibert.com/blog/2018/08/hugo-multilingual-part-1-managing-content-translation/)
- [Go text template](https://pkg.go.dev/text/template)
- Article [Add Contact form to Hugo with Google forms](https://blog.puvvadi.me/posts/add-contact-form-hugo-google-forms/)
- [Add-ons for Hugo](https://hugocodex.org/add-ons/) - Extend Hugo’s functionality

## Contributing to the blog

### Deploy

Website is deploying automatically by CI from `main` branch.

For local deploy use command 
`docker-compose up` (the site will be available at http://localhost:1313).

### Add new post

1. Add new `.md` files the appropriate paths, one for each language (with the next post number):
```
content/en/blog/post-1.md
content/ua/blog/post-1.md
```

2. Post metadata
```
---
title: Post Title
url: '/blog/2023-03-24-post-title'
type: article
omit_header_text: false
featured_image: '/folder/image-name.jpg'
summary_image: '/folder/image-name-short.png'
sharing_image: '/folder/image-name-share.jpg'
twitter_sharing_image: '/folder/image-name-twitter-share.jpg'
alt: 'Picture for Post Title'
keywords: ['some', 'keywords']
date: 2023-03-24
draft: true
---
```
- `title` - post title on banner image.
- `url` - url address for new post must contain post date and post title. For ukraine language use prefix `/ua/` and 
the same url as for English (`'/ua/blog/2023-03-24-post-title'`).
- `type` - must be "article" for blog post.
- `omit_header_text` - there could be two header types, use "false" for big header and "true" for small.
- `featured_image` - background banner image, must be in `/static/` folder. If parameter isn't present will be used 
default site image from home page.
- `summary_image` - image for post list (Blog page), must be in `/assets/` folder.
- `sharing_image` - to share post in LinkedIn and Facebook, the image must be rectangular. You could use the same image 
as summary_image from `/assets/` folder or specify a separate image and place it in `/static/` folder.
- `twitter_sharing_image` - to share post in Twitter, the image must be square. You can reuse an image from `/assets/` 
folder or specify a separate image and place it in `/static/` folder.
- `alt` - for banner image.
- `keywords` - for SEO improvements. It will be added to head metadata.
- `date` - post published date, it is using to sort posts on Blog page.
- `draft` - if "true" post won't be published (and won't be visible even on local deploy).

### Multilingual

Each markdown file that represent separate site page must have appropriation in each site language, otherwise language 
button won't be presented in Menu. If some page isn't translated to other language, please for empty markdown files use 
below text as page content.

For English
```
Unfortunately, the page is not translated into this language.
```

For Ukrainian
```
На жаль, сторінка не перекладена на цю мову.
```

### Images

#### 1. Location

Images could be stored in two places: `/static/` or `/assets/` folders. 
- use `/assets/` folder for images which will be presented in page `main` section (images will be rendered by build);
- use `/static/` folder for background images specified in CSS code `{ background: url(""); }` (banner and header images)
and for images which will be used for sharing but not presented on the site anywhere (such images won't be rendered by build);

#### 2. Add image to a blog post

To add an image between two text paragraphs inside markdown file use shortcode `img`:
```
{{< img src="/blog-images/post-1/image-name.png" alt="Figure 1. Image alt" css_class="img-scale-down">}}
```
Image must be in `/assets/` folder, `alt` will be used as figcaption.

`css_class` - not required; possible options: 
```
.img-width-contain {
  object-fit: contain;
  width: 100%;
}

.img-height-cover {
  object-fit: cover;
  height: 100%;
}

.img-scale-down {
  object-fit: scale-down;
}
```

### Shortcodes

To add text in specific color. Without parameter `color=""` will be used base site color.
```
{{< color-text text="Section title in specific color" color="#FF0000">}}
```

To add link in base site color. It `target="_blank"` link will open in new tab. Without parameter `target=""` link will 
open in the same tab (`_self`)
```
{{< color-link link_title="Link will be opened in new tab" path="https://gohugo.io/" target="_blank" >}}
```