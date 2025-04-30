---
layout: post
title: "How to host blogs with GitHub"
date: 2025-04-24
categories: [How-tos]
tags: [Work hacks]
---

## 1. Why I blog this?
<div style="text-align: justify; font-size: 18px" markdown="1">
Though my first thought of blogging popped up into my mind several years ago, it never transformed into any action. Because there is a mental barrier - I could not find a blogging platform that give me a good balance of simplicity, usability, and controllably, therefore I did not feel comfortable enough to start off. I did not want anything fancy, which are oftentimes distractive. A place that can let me write text, type LaTeX equations, and embed screenshots with ease will be sufficient. Until one day I came across this blog site [Lil's Log](https://lilianweng.github.io/), I was captivated by its simplicity and cleanliness. While I was wondering how she created her blogs, I noticed that the domain name of the site had to do with GitHub. After digging into it, I got to know first time that GitHub could host websites as repositories. All of a sudden, I felted a strong impulse to start blogging with GitHub. Apart from its simplicity, cleanliness, and controllably, which removes my mental barrier mentioned previously, it did not add much new for me to juggle at my work routine. GitHub is a tool I use, though not as frequently as I wish. So, I jumped in learning about steps of using GitHub to create a website for blogging. Nevertheless, there was no single resource that I could follow to finish it end to end. I had to resort to multiple resources to get things through. Accordingly, I feel it is worthwhile to document the steps I have taken to set up my GitHub blog site for the reference of others who may in need on day, at a minimum for myself to refer back.  
</div>

## 2. Concepts
<div style="text-align: justify; font-size: 18px" markdown="1">
**Jekyll**: Jekyll is a static site generator written in Ruby. It is a Ruby gem, analogous to a Python package, for example, numpy.

**Static site generator**: A Static Site Generator is a tool that takes source files (like Markdown, HTML, or templates) and generates a complete static website (a collection of pre-built HTML, CSS, and JavaScript files). Unlike dynamic sites (e.g., WordPress), static sites don’t require a database or server-side processing—they’re just files served directly to users.

**Gem**: Gem is a Ruby library or package, analogous to `pip` packages in Python. Gems are published to [RubyGems.org](https://rubygems.org/). Jekyll is a Ruby Gem. For example, `gem install jekyll` is the way of installing the jekyll package, while `pip install flask` is the way of install the flask package.

**Gemfile**: A Gemfile is a configuration file used in Ruby projects to declare the gems (libraries/packages) your project depends on. It’s managed by Bundler, Ruby’s dependency manager, and ensures consistent gem versions across environments (development, testing, production). It is analogous to requirements.txt in Pytho or pyproject.toml in modern Python with Poetry.

**Bundler**: Bundler is the official dependency manager for Ruby applications. It ensures that your Ruby projects use the correct versions of gems (libraries/packages) by managing installations based on a Gemfile. It is analogous to `pip` + `virtualenv` in Python or `Poetry` in modern Python.

**Bundle**: Bundle is the command-line interface for Bundler, Ruby's dependency manager. Its primary job is to manage your Ruby project's gem dependencies (libraries/packages) . `bundle` commands ≈ `poetry`/`pipenv` commands.
</div>

## 3. Preparation
### 3.1. Install VS Code
<div style="text-align: justify; font-size: 18px" markdown="1">
We are going to use VS Code as the IDE for code writing. Therefore, we will preinstall it. First, go to the download page of [Visual Studio Code](https://code.visualstudio.com/download) to download the Windows installer. Following download, click to open the installer and follow the on-screen instructions and accept defaults to finish the installation. 
</div>

### 3.2. Install Ruby Jeykll
<div style="text-align: justify; font-size: 18px" markdown="1">
We are going to use Jeykll for blogging, and it therefore needs to be preinstalled. First, go to the download page of [RubyInstaller for Windows](https://rubyinstaller.org/downloads/), click on the highlighted installer (e.g., Ruby+Devkit 3.3.8-1 (x64) ) under WITH DEVKIT to download the RubyInstaller. 

Following download, click to open the installer and follow the on-screen instructions and accept defaults to finish the installation. For detail, please refer to the Youtube video [How to Install the Jekyll Static Site Generator on Windows](https://www.youtube.com/watch?v=semqYpqoY_k). Only watch till around 2 mins 47 seconds. The latter part of the video is irrelevant to our task at hand. 

If interested in other installation options, one is referred to [Jeykll Installation](https://jekyllrb.com/docs/installation/)

</div>

## 4. Create a blogging site with GitHub
### 4.1. Overall
<div style="text-align: justify; font-size: 18px" markdown="1">
The Youtube video [How to build your Blog for free on GitHub Pages using Jekyll](https://www.youtube.com/watch?v=m1RYsmOMPLs) gives a fairly straightforward walkthrough, to which one can refer. By and large, it comprises the following steps
1. Find a Jekyll blog template hosted publicly in GitHub, for example [chirpy-starter](https://github.com/cotes2020/chirpy-starter).
2. Log into your own GitHub account, and use this template to create a remote repository of your own. The name of you repository should be `GitHub_account_name.github.io`.
3. Edit the applicable sections in the `_config.yml`, for example, `url`.
4. Clone the GitHub repository to the local drive using `git clone`.
5. Open a Command Prompt (or Git terminal) and navigate to the repository GitHub_name.github.io. In the terminal, type code . to open the VS Code from the directory. Run `bundle` in the VS Code command terminal to install correct version of the gems needed for this project. The gems to be installed are saved in the `Gemfile` in the repository. 
6. Use `bundle exec jekyll serve` to builds the Jekyll static site. The building process will give a server address, something like `Server address: http://127.0.0.1:5000/`. Open it and we will see the locally generated Jekyll site. 
7. Write the first blog. Please refer to [Write the first blog](#42-write-the-first-blog) for detailed steps.
8. Publish the blog to make it visible to the public. Please refer to [Publish the blog](#43-publish-the-blog) for details.
</div>

## 4.2. Write the first blog
<div style="text-align: justify; font-size: 18px" markdown="1">
Open a Command Prompt (or Git terminal) and navigate to the repository `GitHub_name.github.io`. In the terminal, type `code .` to open the VS Code from the directory. On the left sidebar of VS Code, expand `GitHub_name.github.io` under `EXPLORER`, locate the subdirectory `_posts` and expand it. Right click on `_posts` and then choose `New File` and name the file in the format of `year-month-day-blog-name-linked-by-hyphen.md`, for example, `2025-04-23-how-to-host-blogs-with-Github.md`. `.md` file is a plain text file that uses the Markdown markup language for formatting. More detailed instruction can be found at [Jekyll posts](https://jekyllrb.com/docs/posts/).
</div>

### 4.2.1. Header
<div style="text-align: justify; font-size: 18px" markdown="1">
At the top of the `.md` file, type the following header

```
---
layout: post
title: "your post title"
date: year-month-day
categories: [your category]
tages: [your tag]
---
```
</div>

### 4.2.2. Text
<div style="text-align: justify; font-size: 18px" markdown="1">
Writing plain text is just like we writing in other plain text editors, though there are also options to control the formatting of the text. For instance, one can enclose the plain text with the following `<div>...</div>` HTML container, where 
`style="text-align: justify; font-size: 18px"` is CSS inline styling, and `markdown="1"` allows Markdown content inside the `<div>` to be parsed (e.g., `**bold**`, `[links]()`).
```html
<div style="text-align: justify; font-size: 18px" markdown="1">

</div>
```
</div>

### 4.2.3. Code snippet
<div style="text-align: justify; font-size: 18px" markdown="1">
To insert inline code, place single backticks ` before and after the inline code. To insert code blocks, place triple backticks ``` before and after the code block. It is recommended to place a blank line before and after code blocks to make the raw formatting easier to read.
One can refer to [Creating and highlighting code blocks](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/creating-and-highlighting-code-blocks) for details. 
</div>

### 4.2.4. Images
Use `![title](path/example.png)` to embed images. 
### Insert links
Use `[name](link)` to insert inline links. 

### 4.2.5. LaTeX equations
<div style="text-align: justify; font-size: 18px" markdown="1">
Jekyll does not have a native way to display LaTeX equations. To display LaTeX equations in a Jekyll post, we have to  use a JavaScript library like MathJax or KaTeX. These libraries render LaTeX code into mathematical expressions in web browser. We will go with MathJax. 

To start off, use `bundle show your_theme_name` to display the full filesystem path where the Jekyll theme is installed. In this case, since we use the `jekyll-theme-chirpy` theme, type  `bundle show jekyll-theme-chirpy` in the command window. It will then return something like `c:/Ruby33-x64/lib/ruby/gems/3.3.0/gems/jekyll-theme-chirpy-7.2.4`. Open the directory, under the subdirectory `_includes`, find the `head.html` file, and add the following two lines of code under the `<head>` section.

```html
  html <script type="text/x-mathjax-config"> MathJax.Hub.Config({ tex2jax: { inlineMath: [ ['$','$'], ["\\(","\\)"] ], processEscapes: true } }); </script>
  <script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"></script>
```
The first line of the code snippet is for properly displaying the inline equation enclosed by `$ $`, while the second line is for displaying block equations enclosed by `$$ $$`. Now, we can test both with the following. 

The demo of inline equation with `$z^2 = x^2 + y^2$` will yield \\(z^2 = x^2 + y^2\\). The demo of block equation with

```
$$
z^2 = x^2 + y^2
$$
```
will yield

\\[
z^2 = x^2 + y^2
\\]

</div>

### 4.2.6. More styling
<div style="text-align: justify; font-size: 18px" markdown="1">
For more writing and formatting tips, one is referred to [GitHun Doc: Basic writing and formatting syntax](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#images).
</div>

## 4.3. Publish the blog
<div style="text-align: justify; font-size: 18px" markdown="1">
We can keep on editing the blog in the local repository. Once it is finished and you feel comfortable to publish it to the public, we can push it to the GitHub remote repository with the following Git commands. 

```bash
git add.
git commit -m 'message'
git push origin main

```
</div>

## 5. Caveats
<div style="text-align: justify; font-size: 18px" markdown="1">
1. If the local Jekyll site cannot be rendered, please rerun `bundle exec jekyll serve` in the command terminal.
2. If GitHub build failed after `git push origin main`, it might be caused by incorrect Markdown syntax used in the post. Check the build errors for clues. 
3. The use of VPN may cause `Could not connect to server` error after `git push origin main`. If encountered, switch off VPN and try again. 
</div>

## References
1. [How to Install the Jekyll Static Site Generator on Windows](https://www.youtube.com/watch?v=semqYpqoY_k).
2. [Jekyll posts](https://jekyllrb.com/docs/posts/)
3. [How to build your Blog for free on GitHub Pages using Jekyll](https://www.youtube.com/watch?v=m1RYsmOMPLs)