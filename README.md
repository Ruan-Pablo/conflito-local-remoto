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
