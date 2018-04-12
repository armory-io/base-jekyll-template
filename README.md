# READ THIS

When creating posts, in the __date__ field in the .md do not go over the number 9. If you use any number bigger than 9 the post will __not__ render. Probably an easy fix, feel free to make a PR. 


## Features

* Tutorials organised by category
* Two types of tutorials - text and video
* Ability to have a "tutorial series"
* FAQ section
* Disqus comments
* Sticky sidebar for main headings in tutorials
* Optimised for editing in [CloudCannon](http://cloudcannon.com/)
* RSS/Atom feed
* SEO tags
* Google Analytics

## Setup

1. Add your site and author details in `_config.yml`.
2. Add your Google Analytics, Disqus and MailChimp keys to `_config.yml`.
3. Get a workflow going to see your site's output (with [CloudCannon](https://app.cloudcannon.com/) or Jekyll locally).

## Running locally

Once you have this repo checked out, 
1. Download and install Docker
2. Start the server and make changes
    ```
    ./bin/run
    ```

You can view your changes at : `http://localhost:4000` or `http://192.168.99.100:4000` (if you're using docker-machine)

to exit, you can do `ctrl+c`

## Editing

Base is already optimised for adding, updating and removing tutorials, navigation, footer and FAQ information in CloudCannon.

The sticky sidebar in tutorials in populated by pulling out `<h2>` elements from the content.

### Posts

* Add, update or remove a post in the *Posts* collection.
* The tutorials page is organised by categories.
* Change the defaults when new posts are created in `_posts/_defaults.md`.

### Post Series
To create a new series:

* Add a new document to the `sets` collection.
* Set the `title` and `description`.

To add a tutorial/post to a series:
* Add a `set` field to the tutorial front matter which points to the file name of the desired set without the `.md` extention. e.g. If I have a set at `_sets/getting-started.md` I would use this in my tutorial front matter: `set: getting-started`.
* Add a `set_order` field to the tutorial front matter and specify a number. This is the tutorials order in the set.

### Navigation

* Exposed as a data file to give clients better access.
* Set in the *Data* / *Navigation* section.

### Footer

* Exposed as a data file to give clients better access.
* Set in the *Data* / *Footer* section.
