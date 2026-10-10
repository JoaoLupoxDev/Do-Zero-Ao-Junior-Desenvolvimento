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
