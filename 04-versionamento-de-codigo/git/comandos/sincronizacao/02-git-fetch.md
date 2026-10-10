# Baixando Atualizações sem Mesclar (`git fetch`)

---

## 💡 Analogia: Olhando pela Janela da Caixa Postal

Imagine que você está esperando uma carta na sua agência de correios (GitHub). Com o `git fetch`, você vai até a agência, **olha pela janela** para ver se chegou alguma correspondência nova, mas **não pega a carta para dentro de casa ainda**. 

Você apenas atualiza as suas informações sobre o que está lá fora, mantendo o interior da sua casa (seu código atual) totalmente intacto e sem interferências.

---

## 📌 O que é o `git fetch`?

O `git fetch` baixa todas as novidades que aconteceram no repositório remoto (novas branches, commits de outras pessoas), mas **não altera o código em que você está trabalhando no momento**. Ele guarda esses dados em uma "área de visualização segura" (as branches remotas locais, como `origin/main`).

---

## 🛠️ Principais Comandos e Exemplos Práticos

### 1. `git fetch origin`
* **O que faz:** Baixa todas as atualizações do remoto chamado `origin` para o seu computador, atualizando o histórico fantasma do que mudou lá fora.
* **Exemplo:**
  ```bash
  git fetch origin
  ```

### 2. `git fetch --prune` ou `git fetch -p`
* **O que faz:** Além de baixar as novidades, ele **limpa a casa**. Se alguém apagou uma branch lá no GitHub (remoto), esse comando avisa o seu computador e remove os rastros daquela branch que já não existe mais.
* **Exemplo:**
  ```bash
  git fetch --prune
  ```
