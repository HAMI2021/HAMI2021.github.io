# HAMI-web

This is repository for [HAMI lab page](http://127.0.0.1:4000). We use Jekyll to run our Github page.

- [Installation - How to run a Jekyll project in MacOS](#installation---how-to-run-a-jekyll-project-in-macos)
  * [1. install gem & Jekyll](#1-install-gem---jekyll)
  * [2. clone the project from GitHub](#2-clone-the-project-from-github)
  * [3. run the project](#3-run-the-project)
- [User Manual - How can you modify the contents](#user-manual---how-can-you-modify-the-contents)
  * [Member Part](#member-part)
    + [Members Page](#members-page)
    + [Personal Page](#personal-page)
- [Project Codes](#project-codes)
  * [folder: _layouts](#folder---layouts)
    + [1. default.html](#1-defaulthtml)
    + [2. error.html](#2-errorhtml)
    + [3. member.html](#3-memberhtml)
    + [4. misc.html](#4-mischtml)
    + [5. paper.html](#5-paperhtml)
    + [6. post.html](#6-posthtml)
    + [7. project.html](#7-projecthtml)
    + [8. redirect.html](#8-redirecthtml)
    + [9. talk.html](#9-talkhtml)
  * [folder: blog](#folder--blog)
    + [1. folder: _posts](#1-folder---posts)
    + [2. /archive/index.html](#2--archive-indexhtml)
    + [3. index.html](#3-indexhtml)
  * [folder: calender](#folder--calender)
  * [folder: css](#folder--css)
    + [1. folders: bootstrap, font, font-awesome, fonts](#1-folders--bootstrap--font--font-awesome--fonts)
    + [2. custom.scss, katex.scss, solarized.scss, style.css](#2-customscss--katexscss--solarizedscss--stylecss)
  * [folder: error](#folder--error)
  * [folder: guide](#folder--guide)
  * [folder: images](#folder--images)
  * [folder: js](#folder--js)
  * [folder: misc](#folder--misc)
  * [folder: papers](#folder--papers)
    + [1. folder: _posts](#1-folder---posts-1)
    + [2. index.html](#2-indexhtml)
  * [folder: pdfs](#folder--pdfs)
  * [folder: talks](#folder--talks)
    + [1. folder: _posts](#1-folder---posts-2)
    + [2. index.html](#2-indexhtml-1)
  * [folder: team](#folder--team)
    + [1. folder: _posts](#1-folder---posts-3)
    + [2. index.html](#2-indexhtml-2)
  * [404.html](#404html)
  * [index.html](#indexhtml)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

# Installation - How to run a Jekyll project in MacOS

## 1. install gem & Jekyll

```python
# first make sure the version of Ruby >= 2.1
ruby -v
# check whether you have installed gem (By default, Mac installs it automatically)
gem -v
# if both have been set up, you can install Jekyll using gem
gem install jekyll bundler
# check Jekyll is installed successfully
jekyll -v
```

## 2. clone the project from GitHub

- **if you haven't set up git**

    ```python
    # first refer to the following link to download git
    https://git-scm.com/download/mac
    ```

- **if you already set up git**

    ```python
    # run the following command in the terminal
    # then the project will be cloned to your desktop
    cd desktop
    git clone https://github.com/HAMI2021/HAMI-web.git
    ```

## 3. run the project

```python
# enter the **try_construct** folder
# for instance:
cd desktop
cd HAMI-web
cd web

# then type:
bundle exec jekyll serve

# wait a few seconds, you can visit the website at
http://127.0.0.1:4000
```

# User Manual - How can you modify the contents

## Member Part

### Members Page

If you want to modify the layout of Members Page, refer to `/team/index.html` file. For the detailed code explanation of this file, please refer to the next part.

### Personal Page

1. How to add members
    1. First, open `/team/_posts` folder, create a `.md` file naming it with  date+name.

        *Notice*: The project will automatically arrange the layout order of members by date orders and then alphabetical orders. Thus, if you want to modify the order by yourself, you can just change the date in the markdown file.

    2. The contents of the file should be like: 

        The line starting with `//` is the comment and explanation part.

        ```
        // The lines between two `---` define the attributes of each member
        // If you do not want to define some attributes, just skip them
        // If I did not explain them clearly enough, you can refer to the previous `.md` files I implemented

        ---
        layout: member    // this line should be the same for all members' personal page 
        title: e.g. Chen, CHEN    // pls write the member's name here
        position: e.g. Research Assistant    // the position of the member in the lab
        github: xxx     // you can write the **name** (instead of the link, the project will generate the link automatically given the name) of your GitHub account here
        email: xxxx@link.cuhk.edu.cn      // write the email here
        img:       // write the path of your personal image here
        cv:       // write the path of your cv here
        website:     // if you have personal website, you can put its link here
        ---

        // In this part, you can write with markdown grammar, defining the main content you would like to see in your personal page
        ```

2. **How to change the layout of Personal Page**

    For this part, please refer to `_layouts/member.html`, which is specified in the next part as well.

# Project Codes

## folder: _layouts

### 1. default.html

This file declares the basic layout of the first page.

- line 51 - 98: header part
    - line 55 - 61: left part of the header, including the logo and name
    - line 66 - 95: define the navigation bar (blog, papers, ...)
- line 100 -104: body part

    defined by the variable `content`

- line 106: footer part

    currently display nothing

### 2. error.html

This file defines the page of /404. Page displays page title & default content (maybe some warnings defined previously).

### 3. member.html

This file defines the contents to be display on page /team/member-name.

![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/3member.png)

- line 29 - 108: define the left part: CV, twitter, github, google scholar
- line 109 - 199: define the right part
    - line 110 - 112: default introduction part
    - line 126 - 130: define the display of Papers (if any): *paper title with its url*
    - line 145 - 155: define the display of Projects (if any): *project title & project description with its url*
    - line 177 - 193: define the display of Posts (if any): *post title with its url*

### 4. misc.html

`do not find what it is used for yet`

### 5. paper.html

This file declares the basic layout of paper page.

- line 5 - 24: header (paper image, title, authors, year, journal)
- line 28 - 77: left menu bar (pdf, supplement, doi, github)
- line 79 - 81: main content

### 6. post.html

Template of post page.

- line 8 - 53: header part of the post (title, date, authors)
    - line 11 - 13: title
    - line 16: date
    - line 17 - 50
        - line 17 - 25: single author case
        - line 28 - 49: multiple authors case
- line 59 - 76: body part
    - line 62 - 66: image and its url (if any)
    - line 71 -73: post body (main content)

### 7. project.html

`since there is not any sample page on the website, it is a bit hard for me to judge where each part of codes are displayed, and what they are used for`

### 8. redirect.html

this page occurs and warns visitors when the website needs automatically redirect to other page

### 9. talk.html

template of talk page (only title + content)

## folder: blog

### 1. folder: _posts

Put posts (markdown files) in this folder, and fill in the basic information (layout, title, ...) in the header, then it will help generate the page.

### 2. /archive/index.html

This file defines the layout when the tab `index` is selected.

- line 8 - 26: define the two tabs: timeline & index
- line 28 - 71: define the layout of recent posts
    - line 33: display title
    - line 37: display date
    - line 38 - 69: display author / authors

### 3. index.html

This file defines the layout when the tab `timeline` is selected.

- line 9 - 27: define the two tabs: timeline & index
- line 31: limit the maximum recent posts being indicated: 8
- line 34 - 83: define the display of the post header (title, date, authors)
- line 87 - 104: define the display of the post content (image, link, main content)
- line 117 - 129: define `back to top` button

## folder: calender

This folder seems not been used.

## folder: css

This folder defines the style and layout of the whole website.

### 1. folders: bootstrap, font, font-awesome, fonts

This folders seems to be created by default. They defines the basic style of some animations and fonts.

### 2. custom.scss, katex.scss, solarized.scss, style.css

This files defines some basic params and themes of the page. They also define the basic styles (including color, size, background color) of some basic components.

## folder: error

File in this folder define the display when the link is not found. (/404)

## folder: guide

The markdown files in this folder provide a basic tutorial of how to modify the project.

## folder: images

You can put the images needed in this file into the corresponding folders. For instance, if you need to include an image in your paper, just put the image into the papers folder.

## folder: js

Files in this folder defines the basic logics of the website, and it is better not to modify them.

## folder: misc

![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/misc.png)

As is circled in the screenshot, markdown files in the misc folder defines what will display when you click these buttons.

## folder: papers

### 1. folder: _posts

Similar to blog, files under this folder are the papers in markdown files. 

### 2. index.html

Define the display in this page.

![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/2index.png)

- line 10 - 22: how the brief introduction of each paper will be displayed

## folder: pdfs

If you needs to include pdf in your personal page, papers, .etc, just put them into corresponding files.

## folder: talks

### 1. folder: _posts

The talks file.

### 2. index.html

Define the layout of this page.

![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/2index2.png)

- line 8 - 14: header display: Talks
- line 28 - 49: display of each talk
    - line 30: talk title + its url
    - line 33 - 41: `event` at `venue` / `event`
    - line 43 - 46: date & author

## folder: team

### 1. folder: _posts

Personal information needs to be displayed in the member page.

### 2. index.html

Define the layout of this page.

![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/2index3.png)

- line 8 - 14: define the Part I header display: Current members
- line 18 - 37: define the display of each member's basic info
    - line 26 - 29: member name & position
- line 39 - 45: define the Part II header display: Past members
- line 49 - 69: define the display of each past member's basic info

## 404.html

Define the page displayed when 404.

## index.html

Define the page display of home page.

- line 8 - 15: header display
- Part I: Recent posts

   ![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/index.png)

    - line 35 - 42: part I header display: Recent posts
    - line 44 - 104: display of posts
        - line 45: limit the maximum recent posts displayed to 4
        - line 53 - 101: basic information needs to be displayed (title, post date, author)
- Part II: Recent papers

   ![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/index2.png)

    - line 107 - 114: part II header display: Recent papers
    - line 116 - 134: display of papers
        - line 117: limit the maximum recent papers displayed to 4
        - line 118 - 133: basic information needs to be displayed (title, published date)
- Part III: Active Projects

   ![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/index3.png)

    - line 139 - 146: part III header display: Active Projects
    - line 148 - 173: display of projects
        - line 149: limit the maximum recent projects displayed to 4
        - line 150 - 171: basic information needs to be displayed (title-description, updated date and committer)
- Part IV: Misc

    ![Image text](https://github.com/Euphemia111/HAMI/blob/main/img_folder/index3.png)

    - line 177 - 184: part IV header display: Misc
    - line 186 - 205: display of misc
