# Introdução

O Git é um sistema de controle de revisão distribuído rápido, escalável e com um conjunto de comandos extraordinariamente rico que fornece operações de alto nível e acesso total aos internos.

## Status dos estados dos arquivos

🔴 Unmodified - Arquivos não modificados.

🟢 Modified - Arquivos modificados.

🔵 Staged - Arquivos que estão marcados para envio.

## Situações dos arquivos no git

- **Tracked**: Esses são os arquivos que estão sendo acompanhados pelo Git, não possuem alterações pendentes e suas últimas atualizações foram salvas no repositório graças aos comandos `git add` e `git commit`.

- **Staged**: Ficam assim registrados porque foram afetados pelo comando `git add`, embora não pelas últimas alterações. O Git já sabe sobre essas últimas mudanças, mas elas ainda não foram definitivamente submetidas ao repositório porque o comando `git commit` ainda não foi executado.

- **Unstaged**: entenda-os como arquivos *"Tracked, mas não Staged”*. São arquivos que vivem dentro do Git, mas não foram afetados pelo comando `git add`, muito menos pelo `git commit`. O Git possui um registro desses arquivos, mas está desatualizado, suas versões mais recentes são mantidas apenas em disco.

- **Untracked**: São arquivos que NÃO serão rastreados pelo Git. Eles nunca foram afetados pelo `git add`, então o Git não tem registro de sua existência.

# Basic Commands

## Set user data
	git config --global user.name "Fulano de Tal"
	git config --global user.email "you@example.com"
	git config --list

## Basic Start Using 
	git init
	git status
	git add <filepath>
	git commit -m "include subject message" -m "description"

## Log

(..)

## Others comamand

	> Move arquivo para estado Untracked
	git rm --cached Nombre_archivo


	git log
	git init --bare 'is create a SERVER repository
			'details in: https://pt.stackoverflow.com/questions/80182/qual-%C3%A9-a-diferen%C3%A7a-entre-git-init-e-git-init-bare		
	git commit --amend -m "New commit message."
	git merge branch_original (merge to branch current)
	
## Create remote repositories
	git remote	'list the servers
	git remote add  ["alias"] ["directory"]
	git remote -v

## Clone repositores to local machine
	
	git clone [path/to/here/git-e-github/servidor] 'to copy data inside the repo github to local station

## …or create a new repository on the command line

	echo "# logging" >> README.md
	git init
	git add README.md
	git commit -m "first commit"
	git branch -M master
	git remote add origin https://github.com/HelbertAguiar/logging.git
	git push -u origin master

## …or push an existing repository from the command line

	git remote add origin https://github.com/HelbertAguiar/logging.git
	git branch -M master
	git push -u origin master

## Send repo local to remote
	
	git push local master

# Links

	https://devhints.io/git-log

