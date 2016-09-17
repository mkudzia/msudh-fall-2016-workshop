# Git and GitHub for Librarians

## Intro
Hi, I'm Megan! Today we're talking about Git and GitHub for Librarians (and Archivists, and Museum folk, etc.). You can use this outline to follow along with the workshop materials, and to refer back to in the future.

Specifically, here you'll find instructions for doing some basic work with Git or GitHub. So buckle in and let's get started :)

## Git
### Getting started: Opening the command line
#### Mac OS:
1. Open Launchpad OR open a finder window and go to "Applications"
2. Look for the program "Terminal" -- in Launchpad it's probably under "Other," in Finder > Applications it'll be under "Utilities"

#### Windows:
1. Open the Start menu and type `cmd` into the prompt; choose "cmd" from the options that appear

### Command Line Basics
Type the part of the text `that looks like this` for each command to try it out.

#### Mac OS:
1. Figure out what folder you're in: `pwd`
2. Find out what's in that folder: `ls`
3. Leave the Terminal for a moment and create a new folder on the Desktop as you normally would; call it "mmdpTest"
4. Move into that folder using Terminal:
	* Click and drag the folder into your command line window
	* Use the back arrow to get to the beginning of the line and type `cd`
	* It should look like: `cd path/to/mmdpTest`
5. Make a new folder inside that folder using the command line: `mkdir sample_folder` 
6. Make a new file: `touch basic_text.txt`

#### Windows:
1. Figure out what folder you're in: `echo %cd%`
2. Find out what's in that folder: `dir`
2. Leave the command prompt for a moment and create a new folder on the Desktop as you normally would; call it "mmdpTest"
4. Move into that folder using cmd:
	* Change the current directory to the Desktop: `cd Desktop`
	* See what's on your Desktop: `dir`
	* Move into the right folder: `cd path\to\mmdpTest`
5. Make a new folder inside that folder: `mkdir sample_folder` 
6. Make a new file: `fsutil file createnew basic_text.txt 0`

### Git basics:
#### Mac OS:
1. Figure out what folder you're in: `pwd`

#### Windows OS:
1. Figure out what folder you're in: `echo %cd%`

#### Everybody:
1. If applicable, go back up one directory: `cd ..`
2. Now that you're back in the folder you made on your Desktop in the last part of the instructions (mmdpTest), make it a git repository: `git init`
3. You should now have an (invisible) file called .git that keeps track of your git changes!
4. To see what's happening with git and your files: `git status`
5. To add files to what git tracks: `git add sample_folder/basic_text.txt` (*reverse the slash if you're on Windows) -- this "stages" your file(s)
6. To save the changes with a message: `git commit -m "your commit message"`

#### Reversing a change:
1. Updating the commit you just made (with one more change, etc.):
	* `git commit -m "initial commit"` 
	* Oops -- you realize you need to add one more file, make one more change to your CSS, etc.
	* Make changes (make a new file in the top-level folder, "mmdpTest", called forgotten_file.css)
	* `git add forgotten_file.css`
	* `git commit --amend`
2. Un-staging a staged file (you staged a file before you realized you were done with it):
	* Open forgotten_file.css with the text editor of your choice and put some text in it
	* Go back to the command line window
	* `git status` to verify that git knows you've made changes
	* `git add forgotten_file.css`
	* `git status` will show that "forgotten_file.css" is under "Changes to be committed"
	* Realize you weren't done with "forgotten_file.css"
	* Go back to the text editor and add another line of text
	* Go back to your command line window: `git reset HEAD forgotten_file.css`
	* `git status` should show that "forgotten_file.css" is under "Changes not staged for commit"

#### Making a branch:
1. To make a new branch: `git branch devbranch`
2. To "move" to the branch: `checkout devbranch`
3. To do both at once: `git checkout -b devbranch`

#### Merging a branch back into 'master':
NOTE: we're not going to attempt this in the workshop

1. Start by switching back to the master branch: `git checkout master`
2. Merge the branch in: `git merge devbranch`
3. Check to verify that it worked: `git status`

## GitHub
### Cloning a project
1. Open a web browser window
2. Navigate to [https://github.com/gvsulib](https://github.com/gvsulib) and click on "360Link-Reset"
3. Find the row of buttons just above the box that displays all the filenames
	* The first button will say "Branch: master"
	* Look toward the right side of the row for a url in a box; it will be just to the right of a drop-down menu that says "HTTPS"
	* Copy that url
4. Leave your web browser and open a command line window (or go back to the one you had open)
5. Navigate (using `cd`) to the "mmdpTest" folder you made on your Desktop
6. `git clone <pasted url>` -- you can paste the url you just copied into the command line!
7. You should see some processing happening
8. `ls` should show a new folder inside "mmdpTest" called "360Link-Reset"

