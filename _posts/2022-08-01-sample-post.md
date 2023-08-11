---
layout: post
title:  "How to create a blog post"
author: Shannon Tass
description: A sample post instructions on how to create a new blog post
image: 
---

## Steps for creating a new post.  

1. Create a new file in the "_posts" folder called 'YYYY-MM-DD-post-name.md', where YYYY is the year (2023), MM numeric month (01-12), and DD is the numeric day of the month (01-31).  The "post-name" is a short name for the new post with - between words.  **You must use this name convention for all new posts.**  

2.  Make the YML heading.  All pages in the site need to start with a YML heading.  For posts you should use
```
---
layout: post
title:  "Post Name"
author: Your name
description: Short yet informative description
image: /assets/images/blog-image.jpg
---
```
For this theme, the layout should stay as "post".   All the other fields should be updated with the information for your particular blog post.  The blog image should be a .jpg or .png file that you should add to the folder "assets/images".  Don't make it too large or the page will take longer to load (500-800 KB is a good size).  Leave the file path as "/assets/images/" in the header area.  

3.  Write the body of the blog using markdown.  There are a lot of references for markdown available.  I like [Markdown Guide](https://www.markdownguide.org).  There are separate pages for [basic syntax](https://www.markdownguide.org/basic-syntax/), [extended syntax](https://www.markdownguide.org/extended-syntax/), and a [cheatsheet](https://www.markdownguide.org/cheat-sheet/).  


## Internal Links and File
If you want to have a link that points to another location on your site or if you want to include a file (such as an image or videa) you must use the `site.url` and `site.baseurl` variables when making the link reference.  For example, suppose you want a link to point to [about]({{site.url}}/{{site.baseurl}}/about) page.  The reference should be specified as
```
  {{site.url}}/{{site.baseurl}}/about
```
Paths to files should also be referenced with the `site.url` and `site.baseurl` variables.

## Adding Images
Images for the blog will generally but put into the 'assets/images' folder.  You can aslo create a subfolder for images, but you will need to include the subfolder name in the reference link. 

Markdown syntax for including images is `![AltText](path/to/image)`.  For example:
```
![Figure]({{site.url}}/{{site.baseurl}}/assets/images/image5.jpg)
```
![Figure]({{site.url}}/{{site.baseurl}}/assets/images/image5.jpg)


### Resizing images

The image I added in the previous section seems a bit large for this post.  Unfortunately,
there isn't a good way to resize images with markdown, so if you need to resize an image, use html instead of markdown:

```
<img src="{{site.url}}/{{site.baseurl}}/assets/images/image_name.jpg" alt="" style="width:300px;"/>
```

(Example with width set to 300 pixels)
<img src="{{site.url}}/{{site.baseurl}}/assets/images/image5.jpg" alt="" style="width:300px;"/>


(Example with width set to 100 pixels)
<img src="{{site.url}}/{{site.baseurl}}/assets/images/image5.jpg" alt="" style="width:100;"/>



---

## Troubleshooting

Here are some things to keep in mind if your blog appearance isn't going as you planned:

**Problem:  The blog post that I created isn't appearing**

Possible Solutions: 
  - Check your date. GitHub pages won't display blog posts with future dates
  - Check the yaml header.  If there are any special characters in any of the fields, you need to use quotes around the entire field entry.  The most common culprit is the description.  If you're having trouble, try putting quotes around the entire description

---

**Problem:  I know that I made changes to a blog post but the changes aren't appearing**

Possible Solution:
  - Check the header.  If there are any special characters in any of the fields, you need to use quotes around the entire field entry.  The most common culprit is the description.  If you're having trouble, try putting quotes around the entire description.

---

**Problem:  My entire blog has wierd formatting**

Possible Solution:
  - Usually this is an address problem.  Double check your url and baseurl in the _config file
