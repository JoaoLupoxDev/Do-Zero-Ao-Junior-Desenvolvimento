# 🌿 Tópico 3: Ramificação (Gestão de Branches e Mesclagem)

> **💡 A Analogia Central:**
> Imagine que você está escrevendo um livro de sucesso com uma equipe de autores. O livro principal (que vai para as livrarias) está perfeito na versão final. 
> 
> Porém, você deseja testar um final alternativo e um novo personagem sem correr o risco de estragar a história original. O que você faz? Tira cópias das páginas para rabiscar em um rascunho separado. No Git, essas vias de rascunho seguro são chamadas de **Branches** (ramos). Elas permitem que você e sua equipe trabalhem em paralelo sem quebrar o código principal.

<img width="860" height="441" alt="image" src="https://github.com/user-attachments/assets/3294d4b8-a7a1-4424-a7e2-28c8b481a49c" />

---

## 📸 Resumo Visual dos Comandos

| Comando | O que faz no mundo real? | Quando usar? |
| :--- | :--- | :--- |
| `git branch` | Lista ou cria novas folhas de rascunho (ramos). | Quando quiser ver seus ramos ou criar um novo. |
| `git switch` / `git checkout` | Troca a folha de papel que está na sua mesa de trabalho. | Quando for mudar de tarefa. |
| `git merge` | Cola o rascunho aprovado de volta no livro principal. | Quando terminar uma funcionalidade e quiser juntá-la. |

---

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

---

## 2. 🔀 `git-switch-e-checkout` — Transição Moderna e Legada

Utilizado para alternar o seu ambiente de trabalho de um ramo para outro.

### 💻 Lista de Comandos Práticos

```bash
# Transição moderna: Muda para o ramo especificado
git switch nome-do-ramo

# Cria o ramo e faz a transição imediata para ele
git switch -c nome-do-novo-ramo

# Forma tradicional/legada de trocar de ramo
git checkout nome-do-ramo

# Forma tradicional/legada de criar e entrar em um novo ramo
git checkout -b nome-do-novo-ramo

OBS.: Recomenda-se utilizar apenas o git switch, pois é mais atualizado. 
```

### 🔍 Explicação Palavra a Palavra

* **`switch`**: Significa **alternar** ou **trocar**. É o comando moderno e recomendado para navegação entre ramos.
* **`-c`** *(create)*: Cria o ramo informado e já alterna a sua sessão de trabalho para dentro dele.
* **`checkout`**: Comando clássico que significa **registrar saída/entrada**. Embora ainda funcione, hoje prefere-se o `switch` por ser mais simples.
* **`-b`** *(branch)*: Parâmetro usado exclusivamente no `checkout` antigo para criar um ramo antes de trocar.

---

## 3. 🧩 `git-merge` — Mesclagem de Ramificações

Une o histórico de alterações de um ramo secundário ao ramo em que você está situado no momento.

<img width="860" height="292" alt="image" src="https://github.com/user-attachments/assets/6525b6ab-801c-4152-b035-b00b74229e3e" />

### 💻 Lista de Comandos Práticos

```bash
# Traz as alterações do 'ramo-secundario' para o ramo onde você está
git merge ramo-secundario

# Força o registro de um ponto explícito de união no histórico (commit de merge para organização do histórico de alterações e merge)
git merge --no-ff ramo-secundario

# Aborta uma mesclagem em andamento que gerou conflitos manuais (como mesmas linhas de código alteradas por pessoas diferentes e o git identificou)
git merge --abort
```

### 🔍 Explicação Palavra a Palavra

* **`merge`**: Significa **fundir**, **mesclar** ou **unir**. Pega o histórico e combina com o ramo ativo.
* **`--no-ff`** *(no fast-forward)*: Garante que o Git não apenas "avance o ponteiro", mas crie um commit de mesclagem visível no gráfico de histórico.
* **`--abort`**: Cancela a operação de mesclagem atual e restaura o código exatamente ao estado anterior à tentativa de junção.

---

> 📌 **Dica Prática para Iniciantes:**
> Sempre rode o comando `git status` antes de fazer um `switch` ou `merge` para ter certeza de que não deixou arquivos soltos e sem salvar no seu ambiente atual!
