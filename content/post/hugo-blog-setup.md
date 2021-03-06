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
First go to github to create a new repo. Copy the SSH  
```  
git status
git add --all
git commit -m "first commit"
git remote add origin git@github.com:shadowind/Personal_Website.git  
git push -u origin master
```
We need first put some content on the github repo then proceed with initial set up.  
However I encountered fatal error when I do the last step. It says  
"Permission denied (publickey).  
fatal: Could not read from remote repository." 

So this clearly is my SSH error, however I can't remeber what's my github rsa key is. So I used the following guide to help me set up an old SSH key in my computer to github:  

Find existing SSH keys in my mac
```
ls -al ~/.ssh # Make sure I already have some SSH keys
```
Recovering your SSH key passphrase <https://help.github.com/articles/recovering-your-ssh-key-passphrase/>
Adding your SSH key to the ssh-agent <https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#adding-your-ssh-key-to-the-ssh-agent>
Adding a new SSH key to your GitHub account<https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/>
Add the following argument to config.toml file:
> publishDir = "docs"

follow the git add, commit, push process again mentioned above. And see there's a new folder call "docs" also available in repo. Go to settings, in "Github Pages" section, choose build the site on master brance /docs folder. Click Save. Once it's done, it will show the following as the url. 
https://shadowind.github.io/Personal_Website/