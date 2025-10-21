# SP4Sci website

This repository contains the source code of the SP4Sci website.
It is powered by `hugo` ( [https://gohugo.io/](https://gohugo.io/) ).
The idea is to express the content using the Markdown format, then use hugo to generate the actual html and css content.
We use dev ops to autmatically build the server and deploy the new website whenever there is a content update.

## Repository structure

This is the structure of the website with the main files needed to update the website:

```
SP4Sci
|   hugo.toml
|
└---assets
|   |   logo.svg
|   |
|
└---content
|   |   index.md
|   └   page
|       |   author_guide.md
|       |   contacts.md
|       |   ...
|
└---static/image
|   |   logo.png
```

The main idea is that `hugo.toml` defines the properties of the main page, including the website menus.
The content folder describes all the pages.
The remainder folders contain the logo in raster format, and the source make with Inkscape

## How to contribute

The first step is to create a dedicated branch for the change.
Then, we should test locally the change with hugo.
Once done push on the website and perform a merge request to main.
This should trigger the dev ops to build and deploy the new version of the website.
