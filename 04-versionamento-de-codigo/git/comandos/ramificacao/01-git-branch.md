## 1. 📂 `git-branch` — Listando, Criando e Excluindo Ramos

Gerencia a criação e a visualização das suas linhas de trabalho paralelas.

### 💻 Lista de Comandos Práticos

```bash
# Lista apenas os ramos presentes no seu computador (importante para saber em qual branch está trabalhando)
git branch

# Lista todos os ramos (locais e guardados na nuvem)
git branch -a

# Cria um novo ramo com o nome informado
git branch minha-nova-feature

# Renomeia o ramo em que você está trabalhando no momento
git branch -m novo-nome-do-ramo

# Deleta um ramo com segurança (impede se houver código não salvo)
git branch -d nome-do-ramo

# Força a exclusão imediata de um ramo
git branch -D nome-do-ramo
```

### 🔍 Explicação Palavra a Palavra

* **`git`**: Executável da ferramenta que gerencia a versão do projeto.
* **`branch`**: Palavra-chave em inglês para **ramo** ou **ramificação**.
* **`-a`** *(all)*: Exibe **todos** os ramos, incluindo as cópias sincronizadas do GitHub.
* **`-m`** *(move/modify)*: Muta ou move o nome do ramo atual para um novo nome.
* **`-d`** *(delete)*: Opção de exclusão **segura**. O Git valida se o conteúdo já foi integrado antes de apagar.
* **`-D`** *(Delete forçado)*: Exclui o ramo sem checar pendências. Usado para descartar experimentos com falha.
