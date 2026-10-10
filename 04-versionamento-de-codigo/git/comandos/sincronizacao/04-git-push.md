# Publicando Commits (`git push`)

---

## 💡 Analogia: Enviando a Sua Carta para o Mundo

Agora é o inverso. Você escreveu cartas incríveis na sua mesa (fez commits locais) e quer que o mundo inteiro veja. O `git push` é o momento em que você coloca essas cartas no malote e **envia para a agência central na nuvem** (GitHub), para que sua equipe possa ler.

---

## 📌 O que é o `git push`?

É o comando responsável por enviar o histórico dos seus commits locais para o repositório remoto.

---

## 🛠️ Principais Comandos, Opções e Cuidados

### 1. `git push -u origin <branch>`
* **O que faz:** Envia a sua branch atual para o remoto e o parâmetro `-u` (upstream) faz uma **amarração permanente**. A partir desse comando, nas próximas vezes que você quiser enviar ou receber atualizações nessa branch, basta digitar apenas `git push` ou `git pull` sem precisar especificar o nome da branch de novo.
* **Exemplo:**
  ```bash
  git push -u origin minha-feature
  ```

### 2. `git push origin --delete <branch>`
* **O que faz:** Apaga uma branch lá no repositório remoto (na nuvem). Útil quando você já terminou uma tarefa, o código foi aprovado e integrado, e você quer faxinar o GitHub.
* **Exemplo:**
  ```bash
  git push origin --delete branch-antiga
  ```

### 3. `git push --force-with-lease` (O Super Poder Seguro)
* **O que faz:** Às vezes você reescreve o histórico local (com um `amend` ou `rebase`), e o GitHub rejeita o seu `push` porque a linha do tempo diverge. O comando `--force` normal apagaria o trabalho de outros colegas sem dó. Já o `--force-with-lease` é a versão **inteligente e segura**: ele só sobrescreve o remoto se **ninguém mais mexeu** na branch enquanto você estava trabalhando nela.
* **Exemplo:**
  ```bash
  git push --force-with-lease origin minha-branch
  ```
