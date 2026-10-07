# Módulo 04: Versionamento e Colaboração

> **Trilha Do Zero ao Júnior — AWS Student Builder Group SENAI CIMATEC (2026.2)**  
> **Status:** 🟡 Em produção (Módulo Inicial da Trilha)

No desenvolvimento de software profissional, programar sem controle de versões e colaboração em nuvem é impensável. O **Git** é a ferramenta padrão da indústria para registrar a história do código, ramificar funcionalidades e recuperar versões anteriores. Já o **GitHub** é a plataforma colaborativa onde equipes gerenciam demandas, revisam código (*code review*) e integram sistemas.

Este módulo foi estruturado pensando no **Dev Júnior**: nosso foco não é o *overengineering* ou memorização exaustiva de flags obscuras, mas sim construir um **modelo mental sólido**, domínio dos fluxos do dia a dia do mercado e capacidade real de resolver problemas em equipe.

---

## 🎯 Objetivos de Aprendizagem

Ao final deste módulo, você será capaz de:
- Compreender a diferença prática e arquitetural entre **Git** (motor local e distribuído) e **GitHub** (plataforma na nuvem).
- Dominar o ciclo de vida dos arquivos e as zonas de trabalho (*Working Directory*, *Staging Area*, *Local Repository* e *Remote*).
- Escrever commits atômicos e padronizados seguindo a convenção de **Conventional Commits**.
- Criar e gerenciar **branches**, realizar **merges** e resolver **conflitos de código** no editor sem medo.
- Autenticar-se de forma moderna e segura via **Chave SSH (ED25519)** e gerenciar credenciais.
- Trabalhar em equipe através do fluxo de **Issues**, **Pull Requests**, **Code Review** e **GitHub Flow**.
- Compreender as principais **estratégias de versionamento** adotadas por times de engenharia (Gitflow, GitHub Flow e Trunk-based).
- Navegar pelos recursos de automação e gestão do GitHub (**Actions**, **Pages**, **Projects** e **Organizations**).

---

## 🗺️ Mapa de Conteúdos do Módulo

O conteúdo está organizado em dois grandes pilares complementares:

```text
04-versionamento-de-codigo/
├── git/                                    # O motor local e distribuído
│   ├── conceitos/                          # Fundamentos, modelo mental e boas práticas
│   ├── comandos/                           # Dicionário prático comando a comando
│   │   ├── fluxo-basico/                   # init, clone, status, add, commit
│   │   ├── revisao/                        # log, diff, show
│   │   ├── ramificacao/                    # branch, switch-e-checkout, merge
│   │   ├── sincronizacao/                  # remote, fetch, pull, push
│   │   └── historico-e-ajustes/            # restore, reset, revert, stash, rebase, cherry-pick
│   └── guias/                              # Tutoriais passo a passo em cenários reais
│
└── github/                                 # A plataforma colaborativa e fluxo em equipe
    ├── conceitos/                          # Repositories, Issues, PRs, Fork, Code Review, etc.
    ├── recursos/                           # Overview de Actions, Pages, Projects e Organizations
    └── guias/                              # SSH, Contribuição Open Source, GitHub Flow, Perfil, etc.
```

---

## 📚 1. Git: O Motor de Versionamento

### 💡 Conceitos (`git/conceitos/`)
Entenda os porquês antes de memorizar a sintaxe:
1. **[Sistemas de Controle de Versão](git/conceitos/01-sistemas-de-controle-de-versao.md)**: O que é VCS, evolução histórica (centralizados vs. distribuídos) e vantagens do Git.
2. **[Como o Git Funciona por Baixo dos Panos](git/conceitos/02-como-o-git-funciona-por-baixo-dos-panos.md)**: Snapshots vs deltas, integridade criptográfica (hashes SHA) e objetos do Git (`blob`, `tree`, `commit`).
3. **[Zonas de Trabalho e Ciclo de Vida de Arquivos](git/conceitos/03-zonas-e-ciclo-de-vida-de-arquivos.md)**: As 3 áreas locais + o remoto; estados *Untracked*, *Unmodified*, *Modified* e *Staged*.
4. **[Configuração Inicial, Rastreabilidade e Identidade](git/conceitos/04-configuracao-rastreabilidade-e-identidade.md)**: Configurações `--global` vs `--local`, e-mails, rastreabilidade e segurança.
5. **[Anatomia de um Commit, Conventional Commits e Boas Práticas](git/conceitos/05-anatomia-de-um-commit-e-conventional-commits.md)**: Commits atômicos, mensagens semânticas (`feat`, `fix`, `docs`) e o que nunca fazer em um commit.
6. **[Branches e Ponteiros (HEAD)](git/conceitos/06-branches-e-ponteiros-head.md)**: O que são ramificações de verdade, como o ponteiro `HEAD` se move e o que é *Detached HEAD*.
7. **[Estratégias de Integração: Merge vs Rebase](git/conceitos/07-estrategias-de-integracao-merge-vs-rebase.md)**: Fast-forward, 3-way merge commit e Rebase linear. Quando usar cada um.
8. **[O Arquivo .gitignore](git/conceitos/08-o-arquivo-gitignore.md)**: Por que proteger segredos (`.env`, `node_modules/`), regras de padrões e como desrastrear arquivos salvos por engano.

### ⚡ Comandos (`git/comandos/`)
Guias de referência rápida, flags essenciais e exemplos do mundo real organizados por categoria:

* **Fluxo Básico (`fluxo-basico/`)**:
  - [`git init`](git/comandos/fluxo-basico/git-init.md) — Inicializando um repositório local.
  - [`git clone`](git/comandos/fluxo-basico/git-clone.md) — Baixando projetos existentes.
  - [`git status`](git/comandos/fluxo-basico/git-status.md) — Inspecionando o estado da árvore de trabalho.
  - [`git add`](git/comandos/fluxo-basico/git-add.md) — Preparando alterações (incluindo `git add -p`).
  - [`git commit`](git/comandos/fluxo-basico/git-commit.md) — Gravando o snapshot com boas mensagens.

* **Revisão (`revisao/`)**:
  - [`git log`](git/comandos/revisao/git-log.md) — Visualizando o histórico (`--oneline`, `--graph`).
  - [`git diff`](git/comandos/revisao/git-diff.md) — Analisando diferenças no código antes e depois do stage.
  - [`git show`](git/comandos/revisao/git-show.md) — Inspecionando detalhes de commits e tags específicas.

* **Ramificação (`ramificacao/`)**:
  - [`git branch`](git/comandos/ramificacao/git-branch.md) — Listando, criando e removendo ramificações.
  - [`git switch` e `git checkout`](git/comandos/ramificacao/git-switch-e-checkout.md) — Alternando de branch com a sintaxe moderna.
  - [`git merge`](git/comandos/ramificacao/git-merge.md) — Mesclando ramificações e integrando features.

* **Sincronização (`sincronizacao/`)**:
  - [`git remote`](git/comandos/sincronizacao/git-remote.md) — Gerenciando conexões com repositórios remotos.
  - [`git fetch`](git/comandos/sincronizacao/git-fetch.md) — Baixando novidades sem mesclar.
  - [`git pull`](git/comandos/sincronizacao/git-pull.md) — Baixando e integrando novidades da branch remota.
  - [`git push`](git/comandos/sincronizacao/git-push.md) — Enviando commits locais para a nuvem.

* **Histórico e Ajustes (`historico-e-ajustes/`)**:
  - [`git restore`](git/comandos/historico-e-ajustes/git-restore.md) — Descartando alterações de arquivos no working tree ou unstage.
  - [`git reset`](git/comandos/historico-e-ajustes/git-reset.md) — Movendo ponteiros com segurança (`--soft`, `--mixed`, `--hard`).
  - [`git revert`](git/comandos/historico-e-ajustes/git-revert.md) — Desfazendo commits públicos com segurança.
  - [`git stash`](git/comandos/historico-e-ajustes/git-stash.md) — Guardando e resgatando trabalho temporário inacabado.
  - [`git rebase`](git/comandos/historico-e-ajustes/git-rebase.md) — Reaplicando commits e limpando histórico (`git rebase -i`).
  - [`git cherry-pick`](git/comandos/historico-e-ajustes/git-cherry-pick.md) — Aplicando commits pontuais entre branches.

### 🛠️ Guias Práticos (`git/guias/`)
Tutoriais práticos ponta a ponta:
- **[Guia 01: Iniciando seu Primeiro Repositório do Zero](git/guias/guia-01-iniciando-seu-primeiro-repositorio.md)**
- **[Guia 02: Fluxo de Trabalho com Feature Branches](git/guias/guia-02-fluxo-de-trabalho-com-feature-branches.md)**
- **[Guia 03: Resolvendo Conflitos de Merge Passo a Passo](git/guias/guia-03-resolvendo-conflitos-de-merge-passo-a-passo.md)**
- **[Guia 04: Desfazendo Erros e Salvando seu Dia](git/guias/guia-04-desfazendo-erros-e-salvando-seu-dia.md)**
- **[Guia 05: Mantendo o Histórico Limpo com Rebase](git/guias/guia-05-mantendo-o-historico-limpo-com-rebase.md)**
- **[Guia 06: Pausando e Resgatando Trabalho com Stash](git/guias/guia-06-pausando-e-resgatando-trabalho-com-stash.md)**

---

## 🌐 2. GitHub: A Forja Colaborativa

### 💡 Conceitos (`github/conceitos/`)
- **[01. Repositories](github/conceitos/01-repositories.md)**: O que é, visibilidade (público vs. privado), licenças de software e a anatomia de um bom README.
- **[02. Issues](github/conceitos/02-issues.md)**: Rastreamento de bugs, solicitações de funcionalidades e comunicação clara e estruturada.
- **[03. Pull Requests](github/conceitos/03-pull-requests.md)**: Proposta formal de alterações, fluxo de branches remotas e o coração da colaboração.
- **[04. Fork](github/conceitos/04-fork.md)**: Clonagem para a sua conta, a dinâmica do software de código aberto (Open Source) e upstream.
- **[05. Code Review](github/conceitos/05-code-review.md)**: Cultura e boas práticas de revisão de código, comentários em linha, aprovações e etiqueta profissional.
- **[06. Estratégias de Versionamento](github/conceitos/06-estrategias-versionamento.md)**: Modelos de fluxo de equipe: Gitflow, GitHub Flow, Trunk-based Development e conexão com CI/CD.
- **[07. GitHub Flavored Markdown (GFM)](github/conceitos/07-github-flavored-markdown.md)**: Formatação rica, checkboxes de tarefas, blocos de código com highlight e alertas nativos (`[!NOTE]`, `[!TIP]`, `[!WARNING]`).

### ⚙️ Recursos e Ferramentas (`github/recursos/`)
Visão geral prática do ecossistema do GitHub:
- **[01. GitHub Actions](github/recursos/01-actions.md)**: Introdução a CI/CD e automação de tarefas disparadas por eventos do Git (`push`, `pull_request`).
- **[02. GitHub Pages](github/recursos/02-pages.md)**: Hospedagem estática gratuita direto do repositório para documentação e páginas de portfólio.
- **[03. GitHub Projects](github/recursos/03-projects.md)**: Quadros Kanban integrados para organização e gestão ágil de tarefas e sprints.
- **[04. GitHub Organizations](github/recursos/04-organizations.md)**: Ambientes colaborativos corporativos, equipes, permissões de acesso e governança de repositórios.

### 🛠️ Guias Práticos (`github/guias/`)
- **[Guia 01: Configurando Chave SSH do Zero](github/guias/guia-01-configurando-chave-ssh-do-zero.md)**: Geração de par ED25519, cadastro no GitHub e validação no terminal.
- **[Guia 02: Contribuindo em Projeto Open Source (Fork & PR)](github/guias/guia-02-contribuindo-em-projeto-open-source-fork-e-pr.md)**: O ciclo do colaborador externo: Fork, Clone, Upstream, Branch, PR e sincronização.
- **[Guia 03: Fluxo em Equipe (GitHub Flow) na Prática](github/guias/guia-03-fluxo-em-equipe-github-flow-na-pratica.md)**: Da abertura da Issue ao merge do PR com aprovação de pares.
- **[Guia 04: Criando um Perfil e README de Destaque](github/guias/guia-04-criando-um-perfil-e-readme-de-destaque.md)**: Como construir um portfólio profissional atraente no GitHub para recrutadores.
- **[Guia 05: Resolvendo Conflitos de PR no GitHub](github/guias/guia-05-resolvendo-conflitos-de-pr-no-github.md)**: Como contornar conflitos de branch remota via interface web e via terminal local.

---

## 🧭 Como Estudar Este Módulo

Para quem está começando:
1. **Comece pelos Conceitos Fundamentais do Git**: Entenda as 3 zonas e o ciclo de vida dos arquivos antes de rodar os comandos.
2. **Pratique os Comandos de Fluxo Básico**: Inicialize seu primeiro repositório seguindo o **Guia 01**.
3. **Configure sua Conexão Segura**: Siga o **Guia 01 do GitHub** para gerar e cadastrar sua chave SSH.
4. **Avance para Ramificações**: Entenda branches e pratique merges e resolução de conflitos com o **Guia 02** e **Guia 03**.
5. **Colabore**: Entenda Pull Requests, abra seu primeiro PR e aprenda a revisar código em equipe.

---

## 📚 Materiais e Leituras Recomendadas

- 🌐 **AWS SBG CIMATEC**: [Hub de Materiais Recomendados](https://awssbgcimateclanding.vercel.app/)
- 📖 **Livro Gratuito**: [Pro Git Book (Scott Chacon e Ben Straub)](https://git-scm.com/book/pt-br/v2) — A referência definitiva e gratuita em português.
- 🎮 **Interativo**: [Learn Git Branching](https://learngitbranching.js.org/?locale=pt_BR) — O melhor simulador visual interativo de ramificações do mundo.
- 📜 **Padrão de Mensagens**: [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/) — Padrão semântico adotado pela indústria.

---

[⬅️ Voltar para o Roadmap Principal](../README.md)
