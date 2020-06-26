# for .gitignore
# to exclude all svn files - .svn (no wildcards or /)
# to exclude all DW notes directories and files - _notes (no wildcards or /)
 
# to remove a file that is tracked from being tracked
git rm --cached <filename>
 
#to discard all current changes and revert to last commit
git checkout .
 
# clone into current directory
# directory must be empty
git clone git@github.com:user/my-project.git .
 
#force a push to the remote
git push -f <remote> <branch>
 
#Set user name and email
git config --global user.name "Shelane French"
git config --global user.email "french8@llnl.gov"
 
#Read user name and email
git config user.name
git config user.email
 
#List all global config
git config --list
 
#Config file location
~/.gitconfig
 
# Create orphan branch
cd repository
git checkout --orphan orphan_name
git rm -rf .
rm '.gitignore'
git push origin orphan_name

#Inside the .git folder for your project, there is a file /info/exclude. 
#This file has the exact same structure as a .gitignore file, 
#so you can add the file patterns for any files which must be excluded locally, inside that file.

# List commits from one branch to another
git log branch1...branch2  --oneline --reverse --pretty="format:%s

# Create patch:
# Have both files in the same directory
# from within that directory in terminal issue command
 
diff -u originalfile.ext newfile.ext > patchfilename.patch
 
# Apply patch:
# Have patch file within directory 
 
patch -p1 <patchfilename.patch