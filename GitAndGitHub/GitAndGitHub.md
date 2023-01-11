# **Git & GitHub**

## **Intro**

Source control types:
**centralised & decentralised/distributed**

**Centralised** - needs internet connection to access the server with everything one

**Decentralised/distributed** - Mercurial (hg), Git. Most operations are local, so not internet dependent. Central server not required. 

Linus Torvalds created Git to help with developing Linux

<br>
<br>

## **Git Workflow**

1. **WORKING DIRECTORY** - the local storage that holds all your files for the repository. Git is aware of them whether they are used in Git or not. There’s a hidden folder called .git that contains the ACTUAL git repository. This is where the commits are

<br>

2.	**STAGING AREA/GIT INDEX** - holding area for queuing up changes for the next commit. Can move files in and out of here freely without affecting the Git repository

<br>

3.	**COMMIT TO REPOSITORY** (the hidden .git folder) - final changes saved

<br>

4.	**REMOTE REPOSITORY** - Github. Online version of Git basically. 

<br>

Branches - timelines that contain your changes. Default branch is MAIN

<br>
<br>

## **Configure Git**
 <span style="color:#54DBB1">git config --global user.name “Millie Davidson” 
 <br> git config --global user.email “millieaavidson@hotmail.com”</span>

<br>

Check it’s stored this: <span style="color:#54DBB1">Git config --global --list</span>

![Git configuration in Terminal](GitAndGitHub1.png)

<br>
<br>

## **Set up remote & local repositories**

1.	Make your repository on GitHub first

<br>

2.	Clone it using HTTPS clone URL link (click the green code button in repository): 

![Picture of HTTPS clone URL link](../images/4812c3c1e6513a28d61177ae6c27933d8812e6b8f7cbb60564cbded8b4051b4f.png)  
 
Go to your computer’s terminal:
<br>
 <span style="color:#54DBB1">cd</span> to the directory you want to put the repository in 
 <br>
 <span style="color:#54DBB1">git clone www.github.com/put-repository-link-here.git</span>

![Cloning a GitHub repository](GitAndGitHub3.png)  

Git copies your GitHub repository to your local system. Confirm it’s now there with  <span style="color:#54DBB1">ls</span>. You should see the README.md file in there:

![Finding the README file in Terminal](2023-01-10-21-15-00.png)

Always start in the repository folder you are working on. Good idea to start with a clean working tree by checking git status. Pull any changes BEFORE pushing.

In terminal: <span style="color:#54DBB1">git status</span> will tell you which branch you’re on.

![Picture of Git status in Terminal](2023-01-10-21-22-32.png)

^^ this means it’s up to date with the GitHub branch

<br>

3.	Check it works:

Make sure you’re in repository folder. 

<span style="color:#54DBB1">echo “Name of Your Repository” >> test.txt</span>

The >> outputs contents to where you specify. So this would put the text “Name of Your Repository” into the test.txt file. Check file has been made with <span style="color:#54DBB1">ls</span>. 

<span style="color:#54DBB1">cat text.txt</span> to view contents of file

Check <span style="color:#54DBB1">git status</span>

![Checking Git status](2023-01-10-21-28-19.png)
 
If untracked file, means not been added to Git yet. Need to tell Git about it!!

<br>
<br>

4.	<span style="color:#54DBB1">git add name-of-file-here.txt</span> or <span style="color:#54DBB1">git add .</span> (called recursive add??) for all the untracked files

Can add to staging area AND commit in one go - <span style="color:#54DBB1">git commit -am “commit message here”</span>. Can only be done with **tracked files**. Modified files are added to index, then committed. 

Check <span style="color:#54DBB1">git status</span>

![Adding to index and checking Git status](2023-01-10-21-32-10.png)

Tells us changes are in the staging area, ready to be committed. Staging area designed to build up a bunch of changes to be committed as one

<br>

5.	Commit changes 
<span style="color:#54DBB1">git commit -m “your commit message here”</span>

![Commit being made with a message](2023-01-10-21-41-08.png)

<span style="color:#54DBB1">git status</span>

![Git status after commit made](2023-01-10-21-46-08.png)

If everything up to date, will say “Working tree clean”. Now in the third stage. This git command is a LOCAL COMMAND, so it won’t be on GitHub yet. 

<br>
<br>

6.	Push changes to GitHub

Remember to pull before pushing!

In terminal:
<span style="color:#54DBB1">git push origin main</span>
 
![Git push origin main in action](2023-01-10-22-05-06.png)

The origin refers to the remote copy (so in this case, GitHub). Main is the branch we want to push. You’ll be prompted for your username and password (I guess this is why people set up tokens?). Although I’m never prompted for some reason?

I got an error as my email was private:
"remote: error: GH007: Your push would publish a private email address.
remote: You can make your email public or disable this protection by visiting:
remote: http://github.com/settings/emails"

Went to the link and turned off this setting

![Keep my email address private checkbox](2023-01-10-22-07-18.png)
 
All good now

![Git push origin main successful attempt](2023-01-10-22-08-01.png)
 
Verify changes have been successfully made to GitHub by refreshing and checking it there. 

![Test file added to GitHub repository](2023-01-10-22-08-55.png)

<br>
<br>

## **General Git commands**

<span style="color:#54DBB1">git init project-name-here</span> or <span style="color:#54DBB1">git init</span> in the folder you want it in - makes an empty git repository locally 

<span style="color:#54DBB1">ls -al</span> - lists ALL files and folders incl, dot files & folders. You’ll see the .git folder where the git repository lives. 

Root-commit message - tells us this is first commit in the repository 

<span style="color:#54DBB1">cd ..</span> - goes back a directory 

<span style="color:#54DBB1">~</span> tilde goes to home directory~

<span style="color:#54DBB1">~ unzip /Downloads/name-of-file.zip</span> - unzips a zip file

<!--Fork button on the GitHub repository copies someone else’s repository to your own account so you can work on it?-->

<span style="color:#54DBB1">Git pull origin main - updates git repository with your changes on the remote repository</span>

![Git pull origin main in Terminal](2023-01-11-09-27-08.png)

**ALWAYS pull before pushing!**

Tracked files - any file committed into the git repository, index or staging area. Git is aware of it and tracking

<span style="color:#54DBB1">git ls-files</span> - lists all files that git is tracking in the current repository 

<span style="color:#54DBB1">mkdir</span> - make a directory (folder)

For changes that span multiple files, add to staging area and then commit when finished is a good idea

<br>
<br>

## **Logs/history**

<span style="color:#54DBB1">git help log</span> - shows Git commit history. Top is the last commit you did, working backwards in time as you go down. Press q to exit.

When you commit, Terminal will show something like: master ba5b0f0. This number is the SHA-1 identifier for the commit. 

<span style="color:#54DBB1">git log --abbrev-commit</span> - will shorten the commit identifier. Usually only need the first 6/7 characters to uniquely identify a commit (though this grows as your commits do). 

<span style="color:#54DBB1">git log --oneline --graph --decorate</span> - oneline puts entries on one line. Graph brings up ASCII graph, showing branching graph. Decorate adds labels/tags/annotations.

<span style="color:#54DBB1">git log ae6f872…761b911</span> - put the SHA identifiers in, shows you the specified range of commits.

<span style="color:#54DBB1">git log --since=“3 days ago”</span> - shows the commits that have happened in last 3 days.

<span style="color:#54DBB1">git log -- file-name.txt</span> - all the commits that involve this specific file. 

<span style="color:#54DBB1">git log --follow -- path/to/file.txt</span> - shows commit history for that specific file, going through the renames. 

<span style="color:#54DBB1">git show b1986eB63817c7</span> - shows the specified commit with all the details INCL. diff information (what has changed).

<br>
<br>

## **Deleting/unstaging changes**

To **unstage** changes (put it back in your local working directory) - <span style="color:#54DBB1">git reset HEAD file-name-here.txt</span>

If you delete a file and then unstage that deletion, it won’t appear in your working directory (it's not an undo function :(). It’s only back in git staging area. Use the git checkout command - <span style="color:#54DBB1"> git checkout -- file-name-here.txt</span>

Discards changes in the working directory. i.e you’ve deleted your changes from EVERYWHERE and are back on the previous committed version. Check git status and you’ll be back to a clean working tree

Deleting files: if they aren’t tracked by git <span style="color:#54DBB1">git rm file.txt</span> won’t work. So delete normally with <span style="color:#54DBB1">rm file.txt</span>

<span style="color:#54DBB1">rm -rf .git</span> - removes the git folder, thereby removing all traces on git for the repository. <span style="color:#54DBB1">r</span> means recursive and <span style="color:#54DBB1">f</span> is force deletion. **Take CAUTION with this command!**

<br>
<br>

## **Renaming & moving files**

<span style="color:#54DBB1">git mv file-name-here.txt</span> - new-file-name-here.txt - it’s staged the file name change for you! Note, it hasn’t been *committed* though. Good idea to rename files **BEFORE** making changes.

<span style="color:#54DBB1">git mv file-name.txt folder-name</span> - this moves it to the specified folder (if it was same file type, it would write over it?)

If you rename in Bash (Terminal) or in Finder (normally) instead of through Git (e.g <span style="color:#54DBB1">mv file.txt newfile.txt</span> instead of <span style="color:#54DBB1">git mv file.txt newfile.txt</span>), Git sees this as TWO changes - file.txt has been deleted and newfile.txt is a new, untracked file. Sort this with <span style="color:#54DBB1">git add -A</span>. Git status will see you just renamed the file and update accordingly. 

There might be a ../.DS_store_ file that appears when renaming in Finder (just an OS file we don’t want to track). Just <span style="color:#54DBB1">git add file-here.txt</span> . Might want to update the index too - <span style="color:#54DBB1">git add -u</span>

<br>
<br>

## **Git alias**

Instead of typing <span style="color:#54DBB1">git log --all --graph --decorate --oneline</span> to get a neat view, can create your own command for this called a **Git alias**. Check if the command already exists by typing it in (will say if doesn’t exist). 

<span style="color:#54DBB1">git config --global alias.name-of-command-here “--all --commands --you-want-included --here”</span> - global makes it available in EVERY repository i.e all of Git

To modify aliases, need to open git config file - <span style="color:#54DBB1">mate ~/.gitconfig</span> will open it up in TextMate to edit. A text editor is handy for multiple line commits too.

Alias will be under alias section; modify it there

<br>
<br>

## **Untracking files**

If don’t already have a .gitignore file (check with <span style="color:#54DBB1">ls</span>), make one with your text editor - <span style="color:#54DBB1">mate .gitignore</span>

![Checking for a git ignore file in Terminal](2023-01-11-10-23-33.png)
 
Patterns for .gitignore file:
-	Specific file e.g. **a-file.ext**
-	File pattern e.g. **.ext**
-	Folder e.g. **millie/my-folder**

Just write whatever file/folder/pattern it is (**one per line**) and done. NOTE .gitignore file needs adding to Git for version control (<span style="color:#54DBB1">git add .gitignore</span> and <span style="color:#54DBB1">git commit -m “message here”</span>). Pull then push!

<br>
<br>

## **Branching**

Don’t do everything on main!! Make **feature/topic branches** to isolate changes. Integrate them into main branch only once stabilised. Branches are just labels/pointers.

<span style="color:#54DBB1">git branch -a</span> - lists local and remote branches. There will be an asterisk by current active branch

![Picture of which branch I'm on](2023-01-11-11-20-16.png)
 
<span style="color:#54DBB1">git branch new-branch-here</span> - makes a new branch

![New branch created in Terminal](2023-01-11-11-22-08.png)
 
<span style="color:#54DBB1">git checkout new-branch-here</span> - switches branches to the specified one

![Switching branch with git checkout](2023-01-11-11-22-49.png)

<span style="color:#54DBB1">git branch -m my-new-branch new-branch</span> - **-m** moves i.e overwrites and renames the file (here, that would rename to new-branch).

<span style="color:#54DBB1">git branch -d new-branch</span> - deletes branch. Can’t delete a branch you’re already on, FYI!

<span style="color:#54DBB1">git checkout -b new-branch-name</span> - creates new branch AND checks out i.e. creates branch and switches you to it

<br>
<br>

## **Merging**

When merging changes: **REVIEW them first!**

<span style="color:#54DBB1">git diff main develop</span> - first reference branch + second reference branch. Shows you differences between those two branches. Hence the diff

![Comparing branches with git diff](2023-01-11-11-27-23.png)

<span style="color:#54DBB1">git difftool main develop</span> - brings up visual merge differences, like you see on GitHub.

<span style="color:#54DBB1">git merge develop</span> - source branch I want merged into my ***current*** branch. Can delete that branch after merge. This is called fast-forwarding. 

![Merging branch into current one](2023-01-11-11-29-11.png)

I did this one time and got a merge conflict:

![](2023-01-11-11-30-07.png)

Clicked “resolve in merge editor” in my text editor:

![](2023-01-11-11-30-37.png)
  
Found the conflict:

![](2023-01-11-11-31-02.png)
 
Clicked “accept incoming” on the part I wanted to commit. Clicked “complete merge”:

![](2023-01-11-11-31-24.png)
 
Checked git status - all good to try merging develop to main again:

![](2023-01-11-11-32-06.png)

Got the error message again!

![](2023-01-11-11-32-41.png)

Think I forgot to commit the merge 😂. Committed it in Visual Studio Code source control. Then synced changes in same place. All fixed now.

<span style="color:#54DBB1">git merge develop --no-ff</span> - you get a merge commit. So the merge is backed up in case you want to undo it?

<span style="color:#54DBB1">git merge develop -m “Commit message here”</span> - automatic merge with automatic merge commit

If you do changes on one file on one branch and then more changes on same file in main branch, there will be conflicts. Can happen with multiple people working on the same repository. You'll be in a merging state, rather than clean, index etc.   

Once conflicts resolved, git status will say there's an untracked file - that's the original file that Git saved before you resolved the conflicts. It'll end in **.orig**. Probably don't want to track this, so add to .gitignore.

<br>
<br>

## **Pushing & pulling**

I'd added a lot of screenshots to this file and when I went to push it to GitHub, it was taking forever. It seemed like it was doing nothing at all.

I increased the **post buffer** size - <span style="color:#54DBB1">git config --global http.postBuffer 524288000</span>

Checked it configured correctly - <span style="color:#54DBB1">git config --get http.postBuffer</span>

![Increasing and checking post buffer size](2023-01-11-13-39-08.png)

And it pushed in about 10 seconds! Success!

<br>
<br>

## **Credits** 

[GitHub - merge conflicts guide](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-using-the-command-line)

[Stack Overflow - Git push taking ages](https://stackoverflow.com/questions/31895557/git-push-taking-ages)
<!--opt + cmd + v to paste from clipboard directly to markdown doc-->