---
layout: default
title: Actions YML File
parent: Actions Home
grand_parent: index
nav_order: 1
---

# Page Build
``` yml
on:
  pagebuild:
```

Can triger endlessly

# Filters

``` yml
on:
  push:
    paths-ignore:
      - '_data/galleryjson.json'
      - '_includes/gallery.json'
    branches:   
      - master
```
triggers on all push's to master, excecpt of those 2 files (it is unclear what happens if a push includes MORE than those 2 files, it likely triggers). If you figure it out, please update [this page](https://github.com/pauliver/github.tips/new/master)

``` yml
on:
  pull_request:
    paths:
      - '**.jpg'
      - '**.jpeg'
      - '**.png'
      - '**.webp'
    tags-ignore:
      - automerge
```
Triggers on all pull requests that include images, but do not have the tags automerge

# ALL PR triggers

All PR request triggers have extra data of the PR number, actions built for these don't cleanly pull over to other triggers since the other triggers do not have the PR # and wiring it in may not be easy.
