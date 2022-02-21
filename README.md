# Introdução

[Conventions Pattern](https://github.com/HelbertAguiar/basic_git_and_github/blob/master/pattern.md)

O Git é um sistema de controle de versão de arquivo distribuído, rápido, escalável e com um conjunto de comandos extraordinariamente rico que fornece operações de alto nível.

## Status dos estados dos arquivos

🔴 Unmodified - Arquivos não modificados.

🟢 Modified - Arquivos modificados.

🔵 Staged - Arquivos que estão marcados para commit

## Situações dos arquivos no git

- **Tracked**: São os arquivos que estão sendo acompanhados pelo Git, não possuem alterações pendentes e suas últimas atualizações foram salvas no repositório graças aos comandos `git add` e `git commit`.

- **Staged**: São os arquivos que foram afetados pelo comando `git add`, embora não pelas últimas alterações. O Git já sabe sobre essas últimas mudanças, mas elas ainda não foram definitivamente submetidas ao repositório porque o comando `git commit` ainda não foi executado.

- **Unstaged**: entenda-os como arquivos *"Tracked, mas não Staged”*. São arquivos que vivem dentro do Git, mas não foram afetados pelo comando `git add`, muito menos pelo `git commit`. O Git possui um registro desses arquivos, mas está desatualizado, suas versões mais recentes são mantidas apenas em disco.

- **Untracked**: São arquivos que NÃO serão rastreados pelo Git. Eles nunca foram afetados pelo `git add`, então o Git não tem registro de sua existência.

# Comandos Git

## Configura conta no git
	git config --global user.name "Fulano de Tal"
	git config --global user.email "you@example.com"
	git config --global --list

	git config --global 'Configurando o git para iniciar sempre com a branch main ao invés 	da master (git init). A partir da versão 2.28.

## Clona repositorios
	git clone [path/to/here/git-e-github/servidor] 

## Uso Básico 
	git init
	git status
	git add <filepath>
	or git add -i <filepath> (interativo)
	git commit -m "subject message" -m "description message"

## Visualizar log dos commits
	git log
	git log --oneline
	git log -p
	git log --graph --oneline --all
	git log --help
	git log cheatsheet
	gitk
	
-	o comando "gitk" usa interface grafica Tk

## Edita ultimo commit/mensagem
	git commit --amend -m "New commit message."

## Remove um arquivo do git

Após git add, pode ser removido o arquivo com:

	git rm --cached namefile (Arquivo especifico)
	git rm --cached -R .   (Tudo)

## Cria servidor git
	git init --bare 

é criado um servidor remoto, mais detalhes em: \
https://pt.stackoverflow.com/questions/80182/qual-%C3%A9-a-diferen%C3%A7a-entre-git-init-e-git-init-bare		

## Administra repositorios remotos
	git remote							'lista servidores
	git remote add  ["alias"] ["directory"]
	git remote -v
	git remote add [nome-repositorio] [caminho/para/o/repositorio]
	git remote rename [nome-atual] [novo-nome]

## Sincronizando repositorio local com remoto
	git pull							'busca repositorio remoto para local
	git push [remote-repo/origin] [branch-name/main]

## Ramificação
	git branch							'lista branch
	git branch nome-branch				'cria branch
	git checkout nome-branch			'muda de branch
	git switch nome-branch				'muda de branch
	git checkout -b nome-branch			'Cria e entra na branch.
	git branch -m novo-nome				'Renomeia a branch, se estiver dentro dela.
	git branch -m nome-atual novo-nome 	'Renomeia a branch, dentro de outra branch.
	git branch -d nome-branch			'Deleta a branch.
	git fetch							'busca todas as branchs do repo remoto

## Unindo branchs
Caso tenha commits fora da branch principal e ocorreu um BUG na branch principal. Acessar a branch principal, corrigir o erro e rodar o comando.

	git merge nome-branch-secundaria	
	
O merge junta os trabalhos e gera um merge commit. O rebase aplica os commits de outra branch na branch atual.

	git rebase nome-branch-secundaria
	git rebase -i						'interativo

## Linha do tempo e reversões
Viajando no tempo. Não é possível editar e salvar, apenas se criar uma nova branch ou entrar dentro da master.

	git checkout nome-hash

Remove as alterações no código do commit.

	git revert nome-hash

	git reset --hard [coomit]			'limpa staging area e reescreve arvore do commit especificado

	git reset --soft HEAD~2				'Descarta dois ultimos commits ou substitua dois por N para mais.

## Stash

Podem ser considerados "fake commits" ou também commits temporários. 
Antes de usar git stash deve-se usar o comando: *"git add .”*

	git stash list 							'Lista os estados salvos.
	git stash 								'Salva os dados modificados para depois.
	git stash push
	git stash push -m "<stash message>"
	git stash save "mensagem" 				'Salva os dados modificados para depois com contexto.

	git stash drop numero-array 			'Remove as modificações.
	git stash pop numero-array 				'Aplica e remove do stash.
	git stash apply
	

The difference between apply and pop is pop applies the changes in the stash and removes it from the stash too, but apply keeps the changes in the stash even after applying it.

	git stash clear 						'Limpa os estados.
	git stash apply numero-array 			'Aplica as modificações.

## Outros comandos

	git checkout -- nome-arquivo	'Descarta alterações de em arquivo.
	git reset HEAD nome-arquivo		'Desmarcar o arquivo para ser commitado.
	git diff
	git diff --staged
	git show [commit]

## Cherry Pick Commits

Need a feature introduced in a commit in another branch, but the branch is not ready to be merged yet? No, you don’t have to take the 500-year long nap till the branch is merged!

You can just Cherry Pick the commits you require

	git cherry-pick -x <commit hash>		    
	git cherry-pick <commit hash>
	
## Desfazer commits deletados

	git reflog show HEAD
	git reflog
	git reset --hard <commit hash>

NOTE: If you have any local modifications, the command will destroy it as well, so it would be wise to use the stash before resetting

	
## Inicializando repositorio no Github

### …or create a new repository on the command line
	echo "# logging" >> README.md
	git init
	git add README.md
	git commit -m "first commit"
	git branch -M master
	git remote add origin https://github.com/HelbertAguiar/logging.git
	git push -u origin master

### …or push an existing repository from the command line
	git remote add origin https://github.com/HelbertAguiar/logging.git
	git branch -M master
	git push -u origin master

# Links
<ul>
	<li><a href="https://git-scm.com/docs">Git Commands ALL</a></li>
	<li><a href="https://www.toptal.com/developers/gitignore">Gerador .GitIgnore</a></li>
	<li><a href="https://devhints.io/git-log">DevHints</a></li>
	<li><a href="https://git-school.github.io/visualizing-git/">Visualizing GIT</a></li>
	<li><a href="http://git-scm.com/book/en/v2">Git Book</a></li>
	<li><a href="https://lab.github.com/">GitHub Learning Lab</a></li>
	<li><a href="https://www.conventionalcommits.org/en/v1.0.0/">Convetional Commits</a></li>
	<li><a href="https://docs.github.com/pt/github/authenticating-to-github/connecting-to-github-with-ssh">GitHub Docs - Conectar-se ao GitHub com SSH.</li>
</ul>

