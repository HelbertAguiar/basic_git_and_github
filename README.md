# Basic Commands

## Set user
	git config --global user.name "Fulano de Tal"
	git config --global user.email "you@example.com"
	git config --list

## Start Using 
	git init ( inside the folder to delete it )
	git status
	git add <filepath>
	git commit -m "include message"

## Others comamand

	git log
	git init --bare 'is create a SERVER repository
			'details in: https://pt.stackoverflow.com/questions/80182/qual-%C3%A9-a-diferen%C3%A7a-entre-git-init-e-git-init-bare

## Create remote repositories
	git remote	'list the servers
	git remote add  ["alias"] ["directory"]
	git remote -v

## Clone repositores to local machine
	
	git clone [path/to/here/git-e-github/servidor] 'to copy data inside the repo github to local station 

## Send repo local to remote
	
	git push local master

# Links

	https://devhints.io/git-log

