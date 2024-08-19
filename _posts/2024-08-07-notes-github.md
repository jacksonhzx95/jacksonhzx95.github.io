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
 -	Tips: 
	1.) use . to add all files.
	``` bash
	git add .
	```
	2.) Then use [git rm] to remove the unnecessary files/folder
	``` bash
	git rm -r [folder_name]
	git rm [file_name]
	```

4.	 Commit Your Files:
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


## Git Status

### Check Git Status
``` bash
git status
```

### What git status Shows You
- **Untracked Files:** These are files in your working directory that are not being tracked by Git. If you want Git to track them, you need to add them using git add.

 	Example:

{% highlight js linenos %}
Untracked files:
(use "git add <file>..." to include in what will be committed)

somefile.txt
anotherfile.py
{% endhighlight %}

- **Changes Not Staged for Commit:** These are modifications to tracked files that haven’t been staged yet. You can stage them using git add.

	Example:
{% highlight js linenos %}
Changes not staged for commit:
 (use "git add <file>..." to update what will be committed)
 (use "git restore <file>..." to discard changes in working directory)
	
modified:   example.txt
{% endhighlight %}

- **Changes to Be Committed:** These are files that have been staged and are ready to be committed. These changes will be included in the next commit.

Example:

{% highlight js linenos %}
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)

new file:   newfile.txt
modified:   anotherfile.py
{% endhighlight %}

- **Clean Working Directory:** If there are no changes in the working directory or the staging area, Git will report that your working directory is clean.

Example:

{% highlight js linenos %}
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
{% endhighlight %}

## Trouble Shooting
### CONFLICT
1. **Conflict (content)**: Merge conflict in ***.py
     1) Check Status
{% highlight js linenos %}
git status
{% endhighlight %}
     2) Resolve the Conflicts
	We need to manually resolve the conflicts in the files that Git couldn’t merge automatically. The conflicts will be marked in the files, typically looking something like this:

{% highlight js linenos %}
<<<<<<< HEAD
# Your changes
=======
# Changes from the other branch
>>>>>>> other-branch
{% endhighlight %}
 
	For each conflict:

	1.	Edit the file to manually reconcile the differences between the conflicting versions.
	2.	Remove the conflict markers (<<<<<<<, =======, and >>>>>>>).
	3.	Save the file after you’ve resolved the conflict.

     3) Add the Resolved Files to the Staging Area
{% highlight js linenos %}
git add path/to/resolved-file
{% endhighlight %}
     4) Commit the Merge & Push 
  	Once all conflicts have been resolved and the files have been added to the staging area, you can commit the merge.
	
 		After committing the merge, you can continue with your normal Git workflow. For example, if you were merging a feature branch into master, you might now push the master branch to your remote repository:
{% highlight js linenos %}
git commit -m "conflict resolved."
git push origin master
{% endhighlight %}

2. **Conflict (modify/delete)**: Merge conflict in *.py
The conflicts in your output indicate situations where a file was deleted in one branch and modified in another (modify/delete conflicts). In these cases, you’ll need to decide whether to keep the **deletion**, keep the **modifications**, or manually integrate the changes.
	1) Remove the Folder Locally
{% highlight js linenos %}
rm -r path/to/your/folder(files)
{% endhighlight %}
 	2) Remove the Folder from the Git Repository
{% highlight js linenos %}
git rm -r path/to/your/folder
{% endhighlight %}
 	3) Commit and Push
