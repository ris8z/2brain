---
date: 2024-10-11 
tags: 
    - hugo
---

# hugo_new_theme

## first create a new hugo website
`hugo new site mynewsite` 

## than create a new empty theme
`hugo new theme nameofthetheme` 
this will create a new folder in theme that contains:
- layouts/ where u can define your html templates
- static/ contains js/css/image/gits 
- archetypes/ default content templates for specific content type
- theme.toml Metadata about your theme

## setup your theme in config.toml (in the root dir)
`theme = "nameofthetheme"` 
