# Git & GitHub (General)

### How to remove or add to staging area

#### Add files to staging area (before `git push`)

* `git add -A` stages All (include new files, modified and deleted)
* `git add .` stages new and modified, without deleted
* `git add -u` stages modified and deleted, without new

#### Remove files from staging area (unstage)

##### Unstage all

Way 1

* `git reset HEAD .` unstage all files
* `git reset HEAD django_basic/file_name.py` unstage a specific file

Way 2

* git reset

##### Unstage one

* git restore --staged `path`
