# ECE385 CA Documentation

Online website with SystemVerilog and design testing documentation written by CAs.

> Search will not work if you clone this repo and its submodule - delete the line about 'content nil' in assets/search-data.json within the hugo-book theme. This will cause result matching for empty docs, but it _works_ to a degree so it doesn't really matter.

## Submitting PRs with new content

Content on the website is written as markdown files stored in the content/docs folder. Creating a file in there should immediately be reflected in the local build with `hugo server`.

## Updating the Hosted Website

**For CAs with CPanel access**: simply run the deploy script from the main project directory (after cloning) to build and deploy the website to remote. However, ensure that you have the appropriate ssh configuration set up before attempting to do so - ask anyone who you know has pushed to this website before to check that you've done it correctly.
