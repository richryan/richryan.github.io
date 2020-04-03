# Using `blogdown` and `Hugo`
Starting 1/3/2019, I am moving the website to `blogdown`.

## Running the website

The content of the site is located in `richryan.blogdown\public`.
This directory is where the Git repository is located, which includes this `README.md` file.
The content of the website, however, is included in the `content\home` directory.

For example, if you wanted to edit the Research tab, then
this should be done in the `content/research.md` file.

- Requires `blogdown` package
- You can preview the site by running `blogdown::serve_site()`,
which I was able to do in the directory `richryan.blogdown`
- Manage content in the `content` directory in `richryan.blogdown`
- Tabs under the homepage can be configured in `config.toml`
- For *sections* on the main page,
edit *sections* in `richryan.blogdown\content\home`.
These are different Markdown files (`.md` files).
Turn the `active` frontmattter to true in the Markdown file.
- *All* of the content in the `public` directory must be added.
Blog posts, for example, are contained by year.
For example a blog post dated 2019-06-15 is contained in `2019/06/15/hello-world/index.html`.
That HTML file must be included in the GitHub directory.

**NOTE**: I edited how the portrait looks in `themes/hugo-academic/layouts/partials/css/academic.css`,
under `#profile .portrait`. 
`border-radius` modifies how rounded corners are.

**NOTE**: I edited how MathJax works by editing `themes/hugo-academic/layouts/partials/css/academic.css`,
including code labeled with `Added by rwr on 12/8/2019`.

## Creating a new post ##

To create a new post,
create an R markdown file with a .Rmarkdown extension (not .Rmd).
A useful preambamble that I've found to work is:

    ---
    title: "Initial Claims"
    author: "Rich Ryan"
    date: 2020-03-28
    math: true
    tags: ["R"]

    reading_time: false  # Show estimated reading time?
    share: false  # Show social sharing links?
    profile: false  # Show author profile?
    comments: false  # Show comments?

    output: 
      blogdown::html_page:
        toc: true
    ---


- Create the post content, including R content.
- Run `blogdown::serve_site()` on the command line.
- Find the html code associated with the post in the `public` directory; 
for example, `03/28/initial-claims/index.html`.
Commit this file.
- Find the png files associated with the post.
These files are contained under `post` directory and listed under the dated post.
Commit these files.
- Push the new commits to GitHub.
The website should update with the new post.


## Building the `Posts` tab and creating a post ##

### Building ###

This describes the process of creating a page
(see the documentation in the [Hugo Academic documentation](https://sourcethemes.com/academic/docs/managing-content/)).
Content is currently drawn from the `content/post` directory.

- Add `index.md` to the directory `content/posts` directory.
- The `post` directory contains new posts. 
New posts written in `Rmarkdown` be in included as `myfile.Rmarkdown`.

### Creating a post ###

In `content/post/`, create a `.md` file (not an R markdown file).
The 

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

## Useful `git` commands
### Deleting large files
To reduce the repository size, 
I used the "BFG Repo-Cleaner," 
documentation for which can be found [here](https://rtyley.github.io/bfg-repo-cleaner/).
(This, slightly unfortunately, required installing Java.
Nevertheless, see this [link](https://confluence.atlassian.com/bitbucket/reduce-repository-size-321848262.html).
To see that the computer recognizes java,
you could run `>java -version`.)

First, to see the size of the Git repository,
you can run `git count-objects -v`.
The *size-pack* value is the size of your repository when it is pushed to a remote server like GitHub. 
The *size-pack* value is in kilobytes.  
After using BFG, 
you need to remove `reflog` entries that point to old history and
run the garbage collector to purge the old data.
The BFG program recommends running
```
git reflog expire --expire=now --all && git gc --prune=now --aggressive
```

Removing files is done, in the same directory that contains `.git`, along the lines of:
```
java -jar bfg-1.13.0.jar --delete-files f2014_*.pdf
```

To push all the changes back to the GitHub repository, run:
```
git push --all --force
```
and make sure tags are current as well:
```
git push --tags --force
```

You can determine the largest files in the repository by running `bash git_find_big.sh` 
(see [here](https://stubbisms.wordpress.com/2009/07/10/git-script-to-show-largest-pack-objects-and-trim-your-waist-line/)).
