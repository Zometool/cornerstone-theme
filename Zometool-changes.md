# Zometool Changes to Cornerstone

This document describes the key differences in the Zometool variant of the Cornerstone theme for BigCommerce.

All differences from the standard theme can be seen by comparing the `main` branch of [this repository](https://github.com/Zometool/cornerstone-theme) with the `master` branch.  As I write this, note that the `master` is many commits ahead of where we branched `main`, so those commits from standard Cornerstone need to be merged in at some point.

## Layout and Style Changes

There are a number of small stylistic changes, e.g. spacing and font sizes, implemented as modified `.scss` files.

A significant customization is in `templates/components/common/footer.html`, where we have hardcoded some menus, and removed some others.

In the nav menu, the "Models" top-level category is specifically excluded, at the moment; only the "Shop" category appears.

product-view supports `vzome-viewer` if the `vzome` custom field in a product DB entry is set (to a public vZome design URL)

## Model Instructions

Model instructions are accomplished by creating a special kind of product in the database.  A good way to create a model product is to copy an existing one, and carefully change the name, etc.

These are the key requirements for the "product" configuration for a model:
1. Categories MUST have "Models" checked.  This is the specific configuration that causes the theme to give the model "product" a different presentation.
2. Description WILL be displayed next to the model instructions.  Don't make it too verbose!  Link to a page if you have more to say.
3. NO need for images or videos... the thumbnail will be automatically scraped from the GitHub share, next to the vZome file, and the page won't display any images or videos otherwise.
4. Custom fields:
	1. field named "instructions" should contain a public vZome design URL, usually from a GitHub share.  An image with the same path and extension `.png` should be at a similar URL.
	2. field named "difficulty" should have a difficulty level: "expert", "intermediate", or "novice"
5. Other Details:
	1. Brand Name should be "Models"
	2. Visible: MUST BE UNCHECKED
	3. SEO...
	4. Card metadata...

These are additional configurations that are a good idea, but MAY not be required:

1. Availability should be "This product CANNOT be purchased..."
2. Price should be $0
3. Product type should be "downloadable product"