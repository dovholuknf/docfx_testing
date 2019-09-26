# This is the **HOMEPAGE**.
Refer to [Markdown](http://daringfireball.net/projects/markdown/) for how to write markdown files.
## Quick Start Notes:
1. Add images to the *images* folder if the file is referencing an image.

# Madlad txwizard
This guy over at https://github.com/dotnet/docfx/issues/3284#issuecomment-421242922 came up with a crazy brilliant plan to serve the docfx from github and it works the best i've seen thus far.

Here's his summary:

    My solution was fairly straightforward.

    Create the docfx_project directory and generate the documentation as instructed.

    Create a Windows Junction reparse point at docfx_project\_site that points to a docs directory off the main solution directory.

    Ensure that the docfx_project directory contains a 1-byte .gitignore that contains a single asterisk, so that the entire directory is ignored.

    Since docfx_project\_site is empty until I run the generator, it contains no .gitignore file, which has the effect of making everything in the junction directory, docs visible to Git.

    Update my local Git repository, then push everything to GitHub.

    On GitHub, configure GitHub Pages to point to the /docs subdirectory.

    Presto! We have GitHub Pages generated entirely by DocFX.

    There is one deviation from a stock DocFX installation; my API documentation uses a custom template that overrides the Bootstrap styles applied to the navigation bar and the H1 and H2 tags.