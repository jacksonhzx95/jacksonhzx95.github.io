---
layout: post
title: Code repo management
date: 2024-08-06 
last_modified_at: 2024-08-16
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
3.	 Add Files:
  ``` bash
git add [file_name] 
  ```

-   Tips: 
   
	1.) use . to add all files.
	``` bash
	git add .
	```

	2.) Then use [git rm] to remove the unnecessary files/folder
	``` bash
	git rm -r [folder_name]
	git rm [file_name]
	  ```
4. Commit Your Files:
``` bash
git commit -m "Initial commit"
  ```

### 3. Connect Your Local Repository to GitHub

1.	Add Remote Repository:
-	Copy the HTTPS or SSH URL of your GitHub repository from the GitHub website.
-	In your terminal or command prompt, run:
  ``` bash
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPOSITORY_NAME.git
```

### 4. Push Your Code to GitHub

1. Push to Github:
``` bash
git push -u origin master
```
2. Verify Your Upload
	2.1 Check GitHub:
	-	Go to your GitHub repository page.
	-	You should see all your source code files uploaded.


### Additional Steps (Optional)

- Create and Switch to a New Branch:
	``` bash
	git checkout -b new-branch-name
	```

	Then, push this branch to Github:
	``` bash
	git push -u origin new-branch-name
	```

- Pull changes from GitHub:

	If you want to fetch and merge changes from the GitHub repository to your local repository, use:

	``` bash
	git pull origin master
	```

- Collaborate with Others:

	Add collaborators in your GitHub repository settings if it’s a team project.


