---
layout: post
title: How to deploy Reveal.js presentations on GitHub Pages
---

1. Create a new repository on GitHub (i.e. 'reveal_HelloWorld')
2. Clone it on your local machine
3. Clone reveal.js on your local machine ('git clone https://github.com/hakimel/reveal.js.git')
4. Put the content of reveal.js in the reveal_HelloWorld folder
5. Modify the index.html file
6. Create and switch to a new branch ('git checkout -b 'gh-pages')
7. Push
8. From the GitHub website settings:
   - Set the 'gh-pages' branch as default
   - Delete the 'master' branch
9. You are done. The slides are publishe at yourusername.github.io/reveal_HelloWorld
