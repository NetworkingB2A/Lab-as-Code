What is Git?
  - Git allows you to have version control of your software.
  - Git tracks changes to source code.

Why do you need git?
  - git allows sharing code amongst developers




basic Git commands/terminology

create these first when you want to pull down config. This is meta data about youself, needed for git commands later on.
  - git config --global user.name "Your Name"
  - git config --global user.email "your_email@whatever.com"

Creating a new repository
  - create a directory
    - mkdir train_git
    - cd train_git
    - touch "hello_world.txt"
  - create a new repository
    - git init 
      - This will create a repository for your project. That repository is stored on your computer.
    - git add hello_world.txt  
      - This will create a snapshot of the project. you can add a single file or many files. This didnt create the snapshot. this is just the first step. this is acutally called the index in git.
    - git commit -m "adding first file" 
      - This will create a snapshot from your index, and this will add to your repository. good practice to give details about this commit. you should only commit the files that you want to change.
      - git message tips and tricks (https://chris.beams.io/posts/git-commit/)
        - separate subject line from body with a blank line 
        - limit the subject line to 50 characters
        - Capitalize the subject line
        - Do not end teh subject line with a period
        - use the imperative mood in the subject line 
        - Wrap the body at 72 characters
        - Use the body to explain what and why vs how


Data about your current git project ( I cant think of a better name yet.) 
  - git log 
    - this will show the history of the snapshot
    - git log -(number) 
      - this will show a certain number of commits
    - git log --oneline
      - shortens to one line showing commit message and hash code
    - git log --stat 
      - shows number of lines that changed with each commit 
    - git log --diff
      - shows all the differences in the commits
  - git status 
    - This will tell you if your file are commited in your repository.
    - You can put a --short or -s and you will see a shorter list of your current status ( kinda nice when you do this via cli)
  - git diff (some commit id) (some other commit id )
    - this will show the differences in the git snapshots. if you want to see the differences in your commits your must put the commit code. you only need to see the first few digits and not the whole code.
    - if you add a --staged you will see a difference between your commited files and your staged files 
    - if you want to see a difference in your working directory that has not been staged, just use a git diff.
  - git reset  
    - this will allow us to throw changes away 
    - allows us to move commits from history to our working or staging area
    - can be a destructive command
    - three real options
      - use a --soft (commit-ID), move commit to staging area
      - use a --mixed (commit-ID), move commit to the working directory 
      - use a --hard (commit-ID), this will move you commits to the trash
  - git rm (file name)
    - this will stop tracking a file/delete the file
    - Adding a --cached file name will stop tracking the file but will not remove it

git checkout (newer versions of git can use a get switch)
  git checkout (some commit id)
  - this will allow you to change between commits
  - this will take that commit and puts in our file system
  - in doing this you can grab your old commit that was working and have it fix a new bug that you may have introduced 
  git checkout (branch-Name)
  - This will allow you to Branch your code

git merge 
  git merge (main-branch)
  - this will allow you to keep two different versions of code and keep one as you main and the other as your different set of features. (kind of hard to explain for me.)
  - if you have an app. one paid version of the app and the other free version. if you wanted all you paid version of the app to have all the same features of your free version plus some extra features. you would do the following.
    - You would have two branches -Free -Paid
    - you would then switch to your paid version
    - You would then merge to your free version
    - doing this would allow you to take all your code from the free version and have it in your paid branch
    - But it would not work in reverse. your free version would not have the features from your paid version.
  - some terminology
    - Target branch - The branch of where the changes are being pulled from
    - Receiving branch - The branch where your changes are being pulled into.
  - Conflicts in file changes need to be resolved manually

  Fast forward merge
          --0--0--0 <- master branch
         /
  --0--0/

3-way merge
       ---0-0--0--
       /          \
      /            \        
--0--0----0----0----0-- Master



What is a Branch?
  - is a way of taking your code and branching off of your main code.
  - exactly like a tree

What is a conflict?
  - if two commits change the same line of code. you can have a conflict in that code.


!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!

git clone "hyperlink"
   - this is copy a git repository to your computer

git pull
  - this will pull the updates from a online repository to your local repository.

git pull request
  - This one messed with my head for a while, the following is the best way I think to explain it
  - if you make a change to someone else's source code and you want that change to be in the source code you submit a pull request.
  - Meaning you are asking them to pull your changes into their code.


git add (file name or directory location)
  - Also called Git stages
  - This is stage your commit and get them ready for commiting your change
  - You want to stage like code changes together and commit those changes at one time because you can add notes and look at different commits when auditing the code.



git branch 
 
 - To understand this it really helps to understand how pointers work or cnames
 - a Cname is just an alias that points to the main domain name. you can make changes to the cname and never update the original record.
 - In this case i can creating an alias of the code, updating the alias. Then later i may ask my branch to update the main code
 - This actual code will show the branches i have, or i can create and delete my branches 



git pull vs get fetch 
  - I dont really know yet.

The only two reasons i would use this next part is
  - because I dont want to log into the gui
  - I want to change my repository name