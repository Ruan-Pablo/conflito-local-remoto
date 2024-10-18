# Anotações: Resolução de Conflito no Git

Aproveitei um conflito que apareceu neste repositório para treinar a resolução de conflitos no GitHub.

Utilizei **ChatGPT** e **GitHub Docs** como fontes de consulta durante o processo.

Essa branch `repo_errado` foi criada na intenção de testar e salvar tudo.

## O Conflito

O repositório local e o remoto foram inicializados de maneira completamente diferente:

- **Repositório local**: Continha um arquivo `README` (com anotações sobre a situação) e um arquivo de código (apenas para teste).
- **Repositório remoto**: Tinha apenas um `README` relacionado ao desafio que eu estava prestes a fazer.

O conflito ocorreu porque ambos os repositórios possuíam um arquivo `README.md`, porém com conteúdos distintos.

## Passos Seguidos para Resolver o Conflito

### 1. Criação do Repositório Local

O repositório local foi criado com o seguinte objetivo:

- Estudar as modificações que ocorrem ao conectar um repositório local com um repositório remoto incorreto.

Criei uma branch chamada `repo_errado` e cometi as alterações tanto na branch `main` quanto na branch `repo_errado`. Agora, era necessário remover os arquivos da `main` e manter o conteúdo na `repo_errado`, mantendo a `main` vazia.

### 2. Tentativa de Fazer o Pull do Repositório Remoto

Ao tentar fazer o pull do repositório remoto, me deparei com o seguinte erro:

```bash
git pull origin main
```

Retorno:

```bash
fatal: refusing to merge unrelated histories
```

Para forçar o pull dos arquivos do repositório remoto, utilizei:

```bash
git pull origin main --allow-unrelated-histories
```

Resultado:

```bash
Merge made by the 'ort' strategy.
README.md | 2 ++
1 file changed, 2 insertions(+)
create mode 100644 README.md
```

Os arquivos e commits do repositório remoto foram adicionados com sucesso.

---

### 3. Trabalhando com a Branch `repo_errado`

Após o merge da `main`, tentei subir a branch `repo_errado`. O Git sugeriu fazer um **pull request** devido ao conflito entre os `README.md` dos dois repositórios.

#### Comandos sugeridos pelo GitHub:

1. Atualizar o repositório local com as últimas mudanças:

    ```bash
    git pull origin main
    ```

2. Mudar para a branch `repo_errado`:

    ```bash
    git checkout repo_errado
    ```

3. Fazer o merge da branch `main` na `repo_errado`:

    ```bash
    git merge main
    ```

4. Resolver os conflitos e commitar o resultado.

5. Subir as mudanças para o repositório remoto:

    ```bash
    git push -u origin repo_errado
    ```

Após realizar o merge e resolver os conflitos, foi possível fazer o **pull request** no GitHub.

---

Essas foram as anotações e passos seguidos para resolver o conflito que surgiu durante a tentativa de conectar os repositórios.

---

