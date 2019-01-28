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

You can determine the largest files in the repository by running `bash git_find_big.sh` 
(see [here](https://stubbisms.wordpress.com/2009/07/10/git-script-to-show-largest-pack-objects-and-trim-your-waist-line/)).