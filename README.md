## Esse readme foi criado no repositorio local
- repositorio local
- sem conxeção

Esse readme foi criado no repositorio local com a intenção de estudar a modificação que acontece quando:
- o repositorio local se conecta com repositorio errado na nuvem

Criei uma branch repo_errado

fiz um commit so que foi para as duas branchs (main e repo_errado)

agr tenho que apagar os arquivos que estão na branch main e commitar

assim os arquivos permaneceram na branch repo_errado e a main estará vazia

tentando fazer um pull do repositorio remoto me deparo com o seguinte:

git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 969 bytes | 96.00 KiB/s, done.
From https://github.com/Ruan-Pablo/rank-heroi
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> origin/main
fatal: refusing to merge unrelated histories

fazendo separadamente
git fetch origin
git pull origin main

ainda me retorna 
From https://github.com/Ruan-Pablo/rank-heroi
 * branch            main       -> FETCH_HEAD
fatal: refusing to merge unrelated histories

Daí, para forçar o pull dos arquivos em nuvem

`git pull origin main --allow-unrelated-histories`

resultando em:

git pull origin main --allow-unrelated-histories
From https://github.com/Ruan-Pablo/rank-heroi
 * branch            main       -> FETCH_HEAD
Merge made by the 'ort' strategy.
 README.md | 2 ++
 1 file changed, 2 insertions(+)
 create mode 100644 README.md

e adicionou os arquivos e commits que estavam no remoto
---
alterações feitas, agora vamos tentar subir o repositorio local com a branch repo_errado criada no local e sem está no remoto

git pull origin main

subi a main e ele deu um merge, agr quando tentei subir a repo_errado ele fez um pull request

foi possível fazer tudo mas o github sugeriu que eu protegesse a branch e está dando um conflito entre os readmes
nos comandos sugeridos ele pede para fazer um merge com a main

ele pede os seguintes comandos

Step 1: Clone the repository or update your local repository with the latest changes.

git pull origin main

Step 2: Switch to the head branch of the pull request.

git checkout repo_errado

Step 3: Merge the base branch into the head branch.

git merge main

Step 4: Fix the conflicts and commit the result.

See Resolving a merge conflict using the command line for step-by-step instructions on resolving merge conflicts.

> para fazer esse merge ele apagou os arquivos criados (codigos.js) que estava no repo_errado e destacou os conflitos nos readmes

Step 5: Push the changes.

git push -u origin repo_errado

Dps fui no github e ele permitiu fazer o pull request
