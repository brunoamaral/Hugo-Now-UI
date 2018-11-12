---
date: {{ .Date }}
description: ""
draft: false
resources: 
- src: images/
  name: "header"
- src: "gallery/*.jpg"
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
---
