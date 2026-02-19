# gbcroboticsclub

![Jekyll Minima Prototype Screenshot](snapshots\jekyll-minima-prototype-screenshot.png)

# Summary / Highlights
## To run Jekyll (after initial setup), run the following in your terminal within your project repo:
``` bundle exec jekyll serve ```

## Jekyll uses Liquid to generate static HTML pages
When editing Markdown in your Jekyll site, Liquid is quietly turning templates + content into webpages.

# Setup Steps
Jekyll runs on Ruby therefore installing Rubying and Bundler are required
# Install Ruby (with Devkit) + Bundler (Windows)
## 1. Download Ruby Installer
  https://rubyinstaller.org/downloads/
  - Devkit is required or Jekyll will fail
  - Make sure to install MSYS2 development toolchain. This prevents 80% of Jekyll failures later.
![test image](images\RubyInstallerSetup-MSYS2.jpg)

  - Check "ridk install" and click Finish
  ![ridk install checkbox selected](images\ridk-install.png)

  - You should see 3 CLI options. Choose option 3 (because Jekyll dependencies (like ffi, sass, etc.) need a C compiler).
  ![alt text](images\ruby-installer-cli-options.png)

## 2. Restart Environment (important)
    Close: Terminal / Git Bash / Powershell /VS Code

## 3. Verify installation
    Run bash command ```ruby -v```
    Should see: "ruby #.#.#"

    Run ```bundle -v```

## 4. Initialize Bundle
    Run ```bundle init```

# Try out Jekyll

## 1. Add Minima + Jekyll packages
### Update the repo Gemfile to the following:
```
source "https://rubygems.org"

gem "jekyll", "~> 4.3"
gem "minima"
gem "webrick"
```

### Run ```bundle install```
This generates a Gemfile.lock file

### Create _config.yml file with the following:
```
title: Minima Prototype
theme: minima
```

### Create index.md file with the following:
```
---
layout: home
title: Home
---

Minima is running on my project branch.
```

### Run it in terminal
``` bundle exec jekyll serve ```

### Open http://localhost:4000
![Minima Prototype Jekyll Theme](images\minima-prototype-jekyll-theme.png)


# Learning Jekyll
Think of Jekyll as Markdown files -> Jekyll builds -> HTML website

## 3 Things to learn:
1. Front matter
2. Markdown content
3. Layouts

## 1. Front Matter
This is placed at the top of every ```.md``` file.
No front matter means Jekyll will ignore the file.

Sample:
```
---
layout: page
title: About
---
```

Front Matter fields and descriptions:
| Field     | Meaning               |
|-----------|-----------------------|
| layout    | which template to use |
| title     | page title            |
| permalink | /url-extension/       |
| others    | optional settings     |

## 2. Markdown
### Basics
```
Headings
# Big Title
## Section
### Subsection

Lists
- item one
- item two

Links
[My GitHub](https://github.com)

Images (putting them inside assets folder)
![alt text](/assets/image.png)

```

### Minima
Minima expects posts within a ```/_posts/``` folder
These post file have a STRICT naming convention of ```YYYY-MM-DD-name.md```

Sample Post:
```
---
layout: post
title: "First Prototype"
---

This is my first Jekyll post.
```

Minima auto-builds pages based on the following structure:

| Folder    | What happens      |
|-----------|-------------------|
| /index.md | homepage          |
| /about.md | standalone page   |
| /_posts/  | blog feed         |
| /assets/  | images/css        |

