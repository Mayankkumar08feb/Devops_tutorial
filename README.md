# Devops_tutorial
#Easy Git Tutorial with examples on linux platform

git ---- version control system

in 1972 this has been in market called SCCM
in 1982 they have RVS in market
in 1986 they have introduce CVS in market
In 2000 they SVN this is very useful tool in market
        this tool is having a module called as Bikeeper, this is commercial module and Linux kernels are define under this module.
        
in 2005 Bitkeeper ----they are not any more in market.

Linus trovald: Developed own open source version control system, called git with feature.

        -----high speed
        -----data security
        ----data integrity
        ---- user experience
        ---- etc
this has introduce in market April 2005.

let's talk about GIT installation:

#yum install epel-release
#yum install -y git

let's talk about configuration

system -----level configuration

        /etc/gitconfig          -----config file

        #git config --system
user -----level configuration --------Recommend go with this configuration.

        ~/.gitconfig  ------config file

       #git config --global
Project ----level configuration it is in project dir .git ----config Dir

        #mkdir templerun
        #git config
Let's move on Git:-

user details :

        #git config --global user.name "mayank"
        
              #cat .gitconfig ------read the git config file

or,
              #git config --list -----command line to check the deatils

              # ls -la ------you see .gitconfig file on present dir
              
adding user info : -

        # git config --global user.email "mayankkumar08feb@gmail.com"

enable color code:-

        #git config --global color.ui true

        #git config --list
        
Initialized git in my project dir

	  #mkdir templerun

		#cd  templerun

		#ls -la   -----to check if git already initialized in this Dir.
		
	  #git status ----error (fatal: Not a git repository (or any of the parent directories): .git)
  
let's go initialized git in my project dir

    #git init       -------to initialized the command is

    #ls -la         -------you will see .git has been created

    #git status     -------tracking purpose

Repository :

there are three repository are define in git


1. repo ---------it is repository(~/project dir/.git)


2. stage --------  (~/project dir/.git) dir


3. work dir -----project dir


Creating a file for tracking

 #vi templeruninfo.txt

        #git status

        #git add <filename> -----adding a file to staging area

        #git status  ------the file is in staging area

        #git commit -m " message for the commit " <file name>

        #git status   -----Nothing to commit

MODIFICATION and tracking:-

        #vi templruninfo.txt  -----modify this file with some line or some contain

        #git status -------modification message will get in Working Dir.

        #git add templeruninfo.txt

#git status -------modification message will get in Staging Dir.


        #git commit -m " message " templeruninfo.txt

to track commit :

        #git log  --------see latest commit to the git
        #git log -n 5  -----track latest 5 commit
        #git log -n 3 ------track latest 3 commit
        #git log --oneline   ----to see sort from of commit


SHA1 ------ it is 40 charetctor combination which arranged randomly. it is having capability to manage and provide id uniq id nearly 1-2 billions commits. 

        62bbac09a282cbd8c480440cc47089bab79a8a53

        Min project ------sha1 as == 7

        Mid range -------sha1 as ==12

        Big project -------SHa1 as ===15 or own choice

              # git show 62bbac0 ------details for Sha1 commit


        #git show  ------details for latest commit

        #git show HEAD ----details for latest commit

                  HEAD^ ----2nd last commit
                  HEAD^^^---Multiple commit
                  HEAD~25 ----this will show the 25 commit on git
                  HEAD~100..HEAD~50 -----checking commit between 100 and 50th one

Find the difference between files

        #git diff
        #git diff HEAD
        #git diff --staged <file name> ----compare between staging area and local repo
        #git diff -----if there is no file available in staging area
                        then it will compare with local repo and the working dir

#git diff HEAD~100..HEAD~50 -----checking commit between 100 and 50th one

Advance mode:

WORKING DIR:

Delete a file in git.

#Vi readhtml.txt

#git add readhtml.txt
#git commit -m " message" readhtml.txt
#rm readhtml.txt

Till that part we have deleted the file from working dir

to restore the file in working dir

#git checkout -- readhtml.txt
STAGEING DIR:

if a bug file add to staging area then use below command to make file down(mean bring to working Dir) at your working dir

    #git reset HEAD <file>

REPO DIR:-

if a bug file add to REPO DIR then use below command to make file AMEND.

#git --amend -m " amending the file " <file name>
RENAMEING :

#git mv <Old name> <new file>


file ignore:-

if you have multiple file in your project Dir and if don't want to commit those file then create a git ignore file in same DIR

igone the file in git : THERE ARE TWO TYPES OF IGNORE FILE AVAILBLE WITH GIT.

#vi .gitignoe
        *.bak
        *.log
        video/*.mp4
        images/*.jpg
        #!images/git.jpg
        [aeiou]*
        syslog.[0-9].log
GIT IGNORE ON USER LEVEL.

       ~/.gitignore

       #git config --global core.excludefile
        ~/.gitignore_global
TREE structure :

        #git ls-tree HEAD
what is our main stream of development

Branch : it is main place of operation which can be controlled.

  #git branch --list   <-----list of branch availble with git
  #git branch          <---- Current working branch


Creating a new branch to the git

  #git branch <new name>
  #git branch --list

Note : Before jumping to other Branch, make sure everything should be clear to current working Branch

To Jump one Branch to another branch

  #git checkout <branch name>

Note : Before jumping to other Branch, make sure everything should be clear to current working Branch

Create a new branch and jump to that branch

  #git checkout -b <new branch name>
  #git branch

to find out all ACTION IN git

#git log --graph --oneline --decorate --all
#git log --oneline

target is compare a branch

  #git diff master..feature_fix

to merging Branch to other or master branch

  #git branch  --merged newbranch

Note:- you should must present in destination branch
