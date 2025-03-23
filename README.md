# Relatório de Análise de Complexidade de Operações em Árvore AVL - Pokédex

## 📌 Introdução

Este projeto analisa operações realizadas em uma estrutura de dados baseada em uma árvore AVL (Árvore Binária Balanceada). A árvore AVL mantém o balanceamento após cada inserção ou remoção, garantindo melhor desempenho em buscas e manipulações de dados.

As operações analisadas incluem:
- Inserção
- Remoção
- Busca por ID
- Listagem por Pontos de Combate
- Busca por Tipo e Nível

O foco está em entender a complexidade de tempo de cada operação.

---

## 🌳 Operações em Árvore AVL

### 🔧 1. Inserção
A inserção ocorre de forma recursiva, procurando a posição correta para o novo nó. Após isso, o balanceamento é garantido por rotações (à esquerda ou à direita, se necessário).

- **Custo de busca para inserção:** `O(log n)`
- **Custo de balanceamento:** `O(1)` por rotação, mas a verificação e atualização das alturas dos nós custam `O(log n)`
- **Inserção no índice de tipos:** Usando um `HashMap`, a inserção ocorre em `O(1)` em média

**✅ Complexidade total:** `O(log n)`

---

### 🗑️ 2. Remoção
A remoção segue um processo similar à inserção e, após a exclusão do nó, a árvore pode precisar ser reequilibrada.

- **Custo de busca para remoção:** `O(log n)`
- **Custo de balanceamento pós-removal:** `O(log n)`

**✅ Complexidade total:** `O(log n)`

---

### 🔍 3. Busca por ID
A busca segue a lógica de uma árvore binária de busca balanceada.

- **Custo da busca:** `O(log n)`

**✅ Complexidade total:** `O(log n)`

---

### 🥊 4. Listagem de Pokémons por Pontos de Combate
Essa funcionalidade faz uma travessia `in-order` e depois ordena a lista obtida:

1. **Travessia em ordem:** `O(n)`
2. **Ordenação da lista:** `O(n log n)`

**✅ Complexidade total:** `O(n log n)`

---

### 🔥 5. Busca por Tipo e Nível
Usa um índice de tipos implementado como `HashMap<String, Set<Pokemon>>`, permitindo acesso direto ao conjunto de Pokémons de um tipo específico. Depois, aplica-se a filtragem por nível.

1. **Busca no HashMap:** `O(1)` em média
2. **Filtragem por nível:** `O(m)`, onde `m` é o número de Pokémons do tipo. No pior caso, `m = n`.

**✅ Complexidade total:** `O(m)` (média) ou `O(n)` (pior caso)

---

## 🔥 Resumo das Complexidades de Tempo

| Operação | Complexidade |
|----------|--------------|
| **Inserção** | `O(log n)` |
| **Remoção** | `O(log n)` |
| **Busca por ID** | `O(log n)` |
| **Listagem por Pontos de Combate** | `O(n log n)` |
| **Busca por Tipo e Nível** | `O(m)` *(m < n em média)* |

---

## 🏁 Conclusão Final

A árvore AVL garante bom desempenho nas operações essenciais, com complexidade `O(log n)`, mesmo para grandes volumes de dados. A listagem por pontos de combate tem custo `O(n log n)` devido à ordenação, mas mantém boa performance. A busca por tipo e nível é eficiente, com complexidade média `O(m)`.

✅ **Resumo:** A árvore AVL se mostrou uma estrutura robusta e eficiente para armazenar e gerenciar Pokémons, atendendo bem às necessidades de desempenho do sistema.

---
