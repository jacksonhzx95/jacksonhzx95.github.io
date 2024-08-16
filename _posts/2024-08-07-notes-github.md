---
layout: post
title: Code repo management
date: 2024-08-06 
last_modified_at: 2024-08-06
categories: code-repo
tags: [github]
toc:  true
---
Welcome to **Notes for Github**! this section contains useful code in daily maintenance when using GitHub.
{: .message }


## First-time Get a Local Repo

### 1. Create a New Repository on GitHub 
-	Click on the + icon in the top-right corner of the page and select New repository.
-	Enter a Repository name and an optional Description.
-	Choose between a Public or Private repository.
-	(Optional) Add a .gitignore file, a license, and a README file.
-	Click Create repository.

### 2. Initialize a Local Repository
1. 	Open Terminal or Command Prompt:
		Navigate to the directory where your source code is located.
2.	 Initialize Git:
  ``` bash
git init
  ``` 
-	 Add Files:
  ``` bash
git add [file_name] 
  ```
Tips: 

1) use . to add all files 
  ``` bash
git add .
  ```
2) Then use [git rm] to remove the unnecessary files/folder
  ``` bash
git rm -r [folder_name]
git rm [file_name]
  ```
