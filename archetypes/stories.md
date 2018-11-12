---
categories: 
  - 
date: {{ .Date }}
description: ""
draft: false
resources: 
- src: images/
  name: "header"
- src: "gallery/*.jpg"
  name: gallery-:counter
  title: gallery-title-:counter
url: /stories/{{getenv "STORY" | lower }}/{{ getenv "SLUG" | lower }}/
slug:
stories: 
  - {{ getenv "STORY" | lower }}
subtitle: 
tags: 
  - 
title: {{ replace (getenv "SLUG") "-" " " | title }}
options:
  unlisted : false
  showHeader: true
---