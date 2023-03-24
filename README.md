# rs-content

## Links

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

## Contributing to the blog

### Local deploy 

use command 
`docker-compose up` (site will be available at  http://localhost:1313/)

### Add new post

1. Add new `.md` files by the paths (with the next post number):
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
- `title` - Post title on banner image.
- `url` - url address for new post must contain post date and post title. For ukraine language use /ua/ and the same post title in english (`'/ua/blog/2023-03-24-post-title'`).
- `type` - must be "article" for blog post.
- `omit_header_text` - there could be two header types, "false" for big header and "true" for small.
- `featured_image` - background banner image, must be in /static/ folder. If not specified will be used default site image from home page.
- `summary_image` - image for post list page, must be in /assets/ folder.
- `sharing_image` - to share post in LinkedIn and Facebook, the image must be rectangular. You could use the same image as summary_image
- `twitter_sharing_image` - to share post in Twitter, the image must be square.
- `alt` - for banner image.
- `keywords` - for SEO improvements. It will be added to head metadata.
- `date` - post published date, it is using to sort posts on Blog page.
- `draft` - if 'true' post won't be published (and won't be visible even on local deploy).