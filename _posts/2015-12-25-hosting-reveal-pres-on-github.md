---
layout: post
title: How to deploy Reveal.js presentations on GitHub Pages
---

### Create a [new](https://github.com/new) repository on GitHub
   Let's call it `reveal_HelloWorld`
### Clone it on your local machine
    git clone git@github.com:yourusername/reveal_HelloWorld.git
### Clone reveal.js on your local machine
    git clone git@github.com:hakimel/reveal.js.git
### Move the content of reveal.js in the `reveal_HelloWorld` folder
### Modify the `index.html` file
### Create and switch to a new branch
    git checkout -b 'gh-pages'
### Push
    git push
### From the GitHub website repo settings:
   - Set the 'gh-pages' branch as default
   - Delete the 'master' branch

### You are done. The slides are published at yourusername.github.io/reveal_HelloWorld
