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

### How to Create a New Issue and Merge Request in GitLab

1. **Navigate to the Issues Page**  
   Start by going to the Issues page of your project. Click on the **"New Issue"** button.  
   ![Create New Issue GitLab Step 1](.gitlab%2Fimgs%2Fcreate_new_issue_gitlab_1.png)

2. **Enter Issue Details**  
   Fill out all the necessary details for your new issue. If the issue pertains to you, make sure to assign it to yourself. Once you’ve entered all the information, click on **"Create Issue."**  
   ![Create New Issue GitLab Step 2](.gitlab%2Fimgs%2Fcreate_new_issue_gitlab_2.png)

3. **Create a Merge Request**  
   On the next page, click on the **"Create Merge Request"** button.  
   ![Create New Issue GitLab Step 3](.gitlab%2Fimgs%2Fcreate_new_issue_gitlab_3.png)

4. **Configure Merge Request Settings**  
   On this page, you don’t need to change anything else. Ensure you check the following boxes:
    - **Mark as draft**
    - **Delete source branch when merge request is accepted** (you can also select this option later after creating the merge request)  
      Then click on **"Create Merge Request."** You can now make any necessary changes.  
      ![Create New Issue GitLab Step 4](.gitlab%2Fimgs%2Fcreate_new_issue_gitlab_4.png)

5. **Request Review and Mark as Ready**  
   After committing your changes, request a review if needed. Once you're ready, click **"Mark as Ready."**  
   ![Create New Issue GitLab Step 5](.gitlab%2Fimgs%2Fcreate_new_issue_gitlab_5.png)

6. **Finalizing the Merge Request**  
   After marking it as ready, your merge request will be available for merging. Just remember to wait for a review before proceeding. And that’s it!  
   ![Create New Issue GitLab Step 6](.gitlab%2Fimgs%2Fcreate_new_issue_gitlab_6.png)

## Contributing to the blog

## Repository structure

Directory tree:
```
rc-content/
├── .github/
│   └── workflows/
│       └── hugo.yml
├── archetypes/
│   └── default.md
├── assets/
├── content/
├── config/           <-- site configuration
│   └── _default/
│   │   └── hugo.toml
│   └── production/
│       └── hugo.toml
├── data/
├── static/
├── .gitmodules
├── go.mod
├── docker-compose.yml
└── README.md
```

### Deployment Instructions

Website is deploying automatically by CI from `main` branch to 
[GitLab Stage Deploy](https://stage-gitlab.rework-space.com).

For final deployment, make sure to push changes (**ONLY** `content`, theme will be getting from GitLab) from the 
GitLab repository to the GitHub repository at [rc-content](https://github.com/rework-space-com/rs-content). 
The website will be automatically deployed from the main branch of the GitHub repository.

### Local Development

For local deploy use command `docker-compose up` (the site will be available at http://localhost:1313).

Alternatively, after downloading Hugo, you can run `hugo server` (the site will be available at http://localhost:1313).

### Theme Management

If you want to make some changes in theme and to see the changes in real time, make sure to have theme in 
next folder - `themes`. 

To use a different theme, place it in the `themes` folder and update the `hugo.toml` configuration file to reflect 
the new theme name.

To change the version of the theme, modify the `go.mod` file. Locate the line starting with 
`require gitlab.com/rework-space.com/rs-site/rs-theme` and update it to the desired tag or commit SHA, such as 
`v0.0.0-20240806155827-02956aea1959`.

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