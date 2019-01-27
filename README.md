# Using `blogdown` and `Hugo`
Starting 1/3/2019, I am moving the website to `blogdown`.

## Running the website
- Requires `blogdown` package
- You can preview the site by running `blogdown::serve_site()`
- Manage content in the `content` directory in `richryan.blogdown`
- Tabs under the homepage can be configured in `config.toml`

## General Resources
Here are a few resources for using `blogdown`:
- https://blogdown-demo.rbind.io/

Specific to the `hugo-academic` theme:
- add images along the lines of `<img src="img/my-image.something">`
- hard-change the layouts of pages in `layouts/partials/` under the `themes` directory
- Resource for writing content: https://sourcethemes.com/academic/docs/writing-markdown-latex/


# Older `jekyll` version
Directions for updating the website.

- Open Ubuntu for Windows
- Navigate to /mnt/d
- Navigate to U-M Box
- Navigate to richryan.github.io
- Run > bundle exec jekyll serve

Using Jekyll, pages can be hid by removing the title element (and maybe the order element).
