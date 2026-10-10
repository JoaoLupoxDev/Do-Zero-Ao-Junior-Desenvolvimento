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
