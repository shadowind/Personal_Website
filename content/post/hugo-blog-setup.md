---
title: "Hugo Blog Setup"
date: 2017-05-16T11:38:14-07:00
draft: false
---

Hello, welcome to my new blog, here I'm using Hugo to build my static website to store study notes, work project etc.
I followed the tutorial [here]<https://www.youtube.com/watch?v=3wkR8GyDODs>

### Download Hugo
Since I'm using both a mac and a windows, here I setup my the website using mac, in terminal  
```  
brew install hugo  
hugo help # To check the installation sucessfully
```

### Create a website locally
```  
mkdir <dir> # Create a directory to store the content
cd <dir>  # go to the directory
hugo new site <sitename> # Create site
cd <sitename>
hugo new post/hugo-blog-setup.md # Create a new post under "post" folder
vim content/post/hugo-blog-setup.md # Open the markdown file using vim, and edit from terminal
```  
I also need to specify a theme for this website I just created, so go to <https://themes.gohugo.io/tags/blog/> to find simple theme I like, and go to github page of that theme  
```  
git init # make this folder a git file
git submodule add https://github.com/htkoca/theme-hugo-foundation6 themes/<theme_name> # download a theme to "themes" folder  
```  
Copy the config.toml in themes sampleSite to main folder, I can tweek it to suit my need very easily. Now I'm ready to view it from locaslhost, simply type the following and opens on <localhost:1313>:  
```
hugo server
```  

### Push the content to Github

