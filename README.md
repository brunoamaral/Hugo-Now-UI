This theme is built from [Creative Tim](https://www.creative-tim.com/product/now-ui-kit)'s Now-UI Kit.

It includes some features for Hugo users:

- Header photo for homepage, single pages and posts with auto resize and crop
- Content organised by "Stories" and their [^1]
- Instagram section for your photos
- Option to hide the header
- Option to have content unlisted[^2]
- Automatic image galleries using Hugo Resources and photoswipe.js [^3]
- Support for Portuguese and English in i18n folder
- Optional bash script to generate new stories.
- Custom twitter-card tags
- ld+json format for all pages





# config.toml explained

```toml
timeout=20000
baseurl = "https://YOURSITE/"
disqusShortname = ""
googleAnalytics = "UA-XXXXXXXX-1"
languageCode = "en-us"
preserveTaxonomyNames = false
publishdir = "" # where should we build the site?
theme = "now-ui"
title = "SITE TITLE"
copyright = "YOU 2018"

[params]
articlePublisher = "https://facebook.com/USERNAME"
author = "YOUR NAME"
defaultImage = "images/fractal_thumb.jpg" # If no header is present, what image do you want to use in the cards?
description = ""
googleSiteVerification = "" # we verify the site using the head meta tag
googleTagManager = "GTM-XXXXX" # optional, leave empty if you are not using Google Tag Manager.
headerPhoto = "/static/IMG_3710.jpg" # The photo used for the homepage and some of the sections.
instagramSubtitle = "" # the subtitle for the instagram section
logo = "images/logo.png" # your default logo
logohomepage = '' # the image tag for the logo you want to use on the home page
subtitle = ""
summary = ""
twitterHandle = ""
[params.profiles]
facebook = "https://facebook.com/USERNAME"
github = "https://github.com/USERNAME"
twitter = "https://twitter.com/USERNAME"
[params.apis]
googlemaps = "" # In case you want to load the Google Maps javascript on the footer


[privacy]
  [privacy.disqus]
    disable = false
  [privacy.googleAnalytics]
    anonymizeIP = true
    disable = false
    respectDoNotTrack = true
    useSessionStorage = false
  [privacy.instagram]
    disable = false
    simple = true
  [privacy.speakerDeck]
    disable = false
  [privacy.twitter]
    disable = false
    enableDNT = true
  [privacy.vimeo]
    disable = false
  [privacy.youtube]
    disable = false
    privacyEnhanced = true


[mediaTypes]
[mediaTypes."application/json"]
suffixes = ["json"]

[outputs]
	home = [ "HTML", "RSS", "JSON" ]
	section = [ "HTML", "RSS"]
	taxonomy = [ "HTML", "RSS"]


[permalinks]
	post = "/post/:slug/"
	story = "/stories/:sections/:slug"

[sitemap]
	changefreq = "weekly"
	priority = 0.5
	filename = "sitemap.xml"

[taxonomies]
	tag = "tags"
	category = "categories"
	story = "stories"

[social]
	facebook_admin = "XXXXXX"
	facebook_app_id = "XXXXX"

DefaultContentLanguage = "en"

[Languages]

[Languages.en]
weight = 1
LanguageName = "English"

[Languages.en.params]
subtitle = ""
description = ""
# If you are using algolia search
algoliaappid = "" 
algoliaapikey = ""
algoliaindex = ""

[Languages.en.params.authors]
[Languages.en.params.authors.Main]
name = ""
email = ""
thumbnail = ""
facebook = ""
twitter = ""
github = ""
googleplus = ""
bio = ""
authorlink = "/page/the-author/" # The page you are using for your bio
[Languages.en.params.authors.Joe]
name = "Nothing joe"
thumbnail = "joe.jpeg"
facebook = "joe joe"
twitter = "joe joe"
github = "joe joe"
bio = "I was joe before it was cool."

[Languages.en.menu]

[[Languages.en.menu.main]]
name = "The Stories"
url = "/categories/"
weight = 2
post = ""


[[Languages.en.menu.main]]
name = "The Photos"
url = "/instagrams/"
weight = 4
post = "Instagram"

[Languages.pt]
weight = 2
LanguageName = "Portuguese"
subtitle = ""
description = ""

[[Languages.pt.menu.main]]
name = "As Histórias"
url = "/pt/categories/"
weight = 2
post = ""

[[Languages.pt.menu.main]]
name = "As Fotos"
url = "/pt/instagrams/"
weight = 4
post = "Instagram"

pygmentsOptions=""
pygmentsCodefences=true
pygmentsStyle="monokai"
pygmentsUseClasses=true

[imaging]
# See https://github.com/disintegration/imaging
# Imaging supports image resizing using various resampling filters. The most notable ones:

# NearestNeighbor - Fastest resampling filter, no antialiasing.
# Box - Simple and fast averaging filter appropriate for downscaling. When upscaling it's similar to NearestNeighbor.
# Linear - Bilinear filter, smooth and reasonably fast.
# MitchellNetravali - А smooth bicubic filter.
# CatmullRom - A sharp bicubic filter.
# Gaussian - Blurring filter that uses gaussian function, useful for noise removal.
# Lanczos - High-quality resampling filter for photographic images yielding sharp results, but it's slower than cubic filters.
resampleFilter = "lanczos"

# Defatult JPEG quality setting. Default is 75.
quality = 90

# Anchor used when cropping pictures.
# Default is "smart" which does Smart Cropping, using https://github.com/muesli/smartcrop
# Smart Cropping is content aware and tries to find the best crop for each image.
# Valid values are Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
anchor = "smart"

```





# Front matter explained

```yaml
---
date: {{ .Date }}
description: ""
draft: false
resources: 
- src: images/ # image to use in the header of this post/page
  name: "header"
- src: "gallery/*.jpg" # if you want to use the gallery shortcode, place all your images in the `gallery` folder.
  name: gallery-:counter
  title: gallery-title-:counter
  slug:
  stories:
  subtitle: 
  tags: 
  - 
    categories: 
  - 
    title: "{{ replace (getenv "SLUG") "-" " " | title }}"
options:
  unlisted: false
  showHeader: true
# options to hide the post from listings and to show or hide the header
---
```



# Stories

A story is a collection of posts around the same subject and they can be featured on your homepage. To create one, start a new folder inside `content/` and write _index.md with something like this:

```yaml
---
resources:
- src: "image-2011FAA1EC9D-1.jpeg"
  name: "sectionHeader"
story_slug: museum-tour
story_title: "Bruno's Museum Tour"
story_subtitle: "An unpretentious walk around Lisbon's Museums"
story_description: "This may or may not become a full section with a few Museums in Lisbon, time will tell."
story_color: "#ffffff"
story_header_height: "400px" #deprecated
story_published: true
options:
  unlisted: false
story_featured: false #if true, it will be shown on the frontpage as a card
---

```



# Using galleries

In your front matter:

```yaml
resources: 
- src: gallery/IMG_1801.jpg
  name: "header"
- src: "gallery/*.jpg"
  name: gallery-:counter
  title: gallery-title-:counter
```

In your content, use the shortcode and make sure the folder names match. This allows you to have two galleries in the same page.

`{{% gallery folder="gallery" title="Escher in Lisbon" %}}`





# ./new help

I built this script for my own use, most of the features will not fit your needs. 

**post** : creates a new post, sintax is :: new post TITLE-with-dashes
**story** : creates a new post inside a story, sintax is ::  new story `STORY-NAME` `title-with-dashes`
**paginas-tantas** : creates a new post insite the paginas-tantas story
**publish** : adds all files to git and commits the changes to the current branch
**deploy** : pushes any commits to origin and connects to the DeLorean server to run the build script

[^1]: See the example content in stories/simple-things
[^2]: remember to delete the unlisted section if you want to keep it hidden from prying eyes.
[^3 ]: Look in the museum-tour story for examples 



