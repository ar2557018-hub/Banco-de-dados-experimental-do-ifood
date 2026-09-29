# 🍽️ Comidex - Banco de Dados Relacional

Este repositório contém a modelagem, os scripts de criação, inserções e consultas SQL avançadas desenvolvidas para o sistema **Comidex**, um projeto acadêmico focado em gerenciamento de pedidos e entregas de restaurantes.

---

## 🛠️ Tecnologias Utilizadas

* **SGBD:** PostgreSQL
* **Ferramentas:** VS Code, Git/GitHub
* **Linguagem Procedural:** PL/pgSQL

---

## 📐 Estrutura do Banco de Dados

O ecossistema do banco é composto por 6 tabelas principais:

* **`usuarios`**: Cadastro de clientes do sistema.
* **`estabelecimentos`**: Restaurantes e comércios parceiros.
* **`produtos`**: Itens disponíveis no cardápio.
* **`entregadores`**: Informações dos profissionais de entrega.
* **`pedidos`**: Registro dos pedidos contendo totais, taxas e situação.
* **`pedido_itens`**: Tabela associativa que detalha os produtos pertencentes a cada pedido.

---

## 📑 Funcionalidades e Scripts Desenvolvidos

### 1. Consultas e Filtros (DQL)
* **Agrupamento e Médias (`GROUP BY` / `AVG`):** Consulta do valor médio gasto por cada usuário em seus pedidos com tratamento numérico para casas decimais.
* **Filtros de Agregação (`HAVING`):** Filtragem de estabelecimentos com faturamento acumulado acima de determinados limites.
* **Extração de Datas (`EXTRACT` / `JOIN`):** Relatórios de vendas com totalização de itens comercializados agrupados por mês e ano.

### 2. Objetos Procedurais (PL/pgSQL)

#### 🔄 Stored Procedures
* **`inserir_novo_usuario`**: Automatiza a inserção de novos clientes preenchendo as colunas de data/hora (`data_criacao` e `data_atualizacao`) com a estampa de tempo atual (`CURRENT_TIMESTAMP`).
* **`atualizar_preco_produto`**: Atualiza o valor de um produto via ID e sincroniza a coluna `data_atualizacao`.

#### ⚙️ Functions (Funções)
* **`contar_pedidos_por_estabelecimento`**: Recebe o ID de um estabelecimento e retorna o total de pedidos vinculados a ele.
* **`obter_ultimo_pedido`**: Recebe o ID de um usuário e retorna a estampa de data/hora do seu pedido mais recente.

#### 👁️ Views (Visões)
* **`vw_detalhes_pedidos`**: Consolida os dados detalhados de pedidos ligando nomes de usuários, estabelecimentos, endereço de entrega e valores finais.
* **`vw_produtos_estabelecimentos`**: Relatório de catálogo que mapeia a disponibilidade dos produtos para cada estabelecimento associado.

---

## 🚀 Como Executar o Projeto

1. Clone o repositório em sua máquina:
   ```bash
   git clone [https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git](https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git)
