# 📚 Caderno Temático: Fundamentos de SQL/Banco de Dados

> Projeto desenvolvido com o NotebookLM (Google) como parte do desafio **"Treinando uma IA de Aprendizagem"** da DIO — explorando IA como ferramenta ativa de estudo, curadoria de fontes e organização do conhecimento.

---

## 🎯 Contexto e Objetivos

**Assunto escolhido:** Fundamentos de SQL e Banco de Dados

**Por que esse tema:** Estou cursando Database Technology e buscando minha primeira oportunidade como analista/estagiário de dados. SQL é uma das competências mais cobradas em processos seletivos da área, e usei o NotebookLM como uma ferramenta de estudo ativo — testando prompts estratégicos para consolidar os fundamentos e validar até onde a IA consegue se manter fiel às fontes carregadas, em vez de simplesmente aceitar respostas prontas.

**Objetivos de estudo com este material:**
- [ ] Consolidar os conceitos fundamentais de SQL (DDL, DML, DQL)
- [ ] Entender modelagem relacional e normalização
- [ ] Praticar comandos de JOIN e suas variações
- [ ] Criar um material de consulta rápida para revisões futuras

---

## 🔍 Curadoria de Fontes

Fontes abertas selecionadas e carregadas no NotebookLM:

1. **PostgreSQL 18 Documentation — The SQL Language** — https://www.postgresql.org/docs/current/tutorial-sql.html — documentação oficial, cobre criação e gerenciamento de tabelas, consultas avançadas e junções
2. **W3Schools SQL Tutorial** — https://www.w3schools.com/sql/ — referência prática de sintaxe SQL (DDL, DML, DQL)
3. **freeCodeCamp — Database Normalization: 1NF, 2NF, 3NF** — https://www.freecodecamp.org/news/database-normalization-1nf-2nf-3nf-table-examples/ — abordagem pedagógica, exemplo único evoluindo passo a passo pelas formas normais
4. **DigitalOcean — Database Normalization Tutorial** — https://www.digitalocean.com/community/tutorials/database-normalization — guia mais completo e técnico, cobre 1NF a BCNF, anomalias e trade-offs de desnormalização
5. **ThoughtSpot SQL Tutorial** — https://www.thoughtspot.com/sql-tutorial — conteúdo voltado a SQL aplicado à análise de dados e BI

---

## 🧪 Engenharia de Prompts e "Cicatrizes"

Documentação do processo de testes de prompts no NotebookLM — incluindo o que funcionou, o que precisou de ajuste, e as dificuldades encontradas.

### Prompt 1 — Resumo geral
**Prompt usado:**
> "Resuma os conceitos fundamentais de SQL presentes nas fontes, organizando por: comandos DDL, DML e DQL."

**Resposta obtida (resumo):** A IA organizou o conteúdo em três blocos claros — DDL (CREATE TABLE, ALTER TABLE, DROP TABLE, CREATE/DROP DATABASE, CREATE INDEX, além dos conceitos de chave primária, chave estrangeira e normalização), DML (INSERT INTO, UPDATE, DELETE) e DQL (SELECT, WHERE, ORDER BY, JOIN, funções de agregação, GROUP BY/HAVING). Cada afirmação veio acompanhada de citações numeradas remetendo às fontes específicas.

**Observações:** Funcionou muito bem de primeira — a resposta veio bem estruturada e claramente ancorada nas fontes (todas as afirmações citadas), sem necessidade de refinamento.

---

### Prompt 2 — Comparação entre fontes
**Prompt usado:**
> "Compare como as fontes definem e explicam normalização — há diferenças de profundidade ou abordagem entre elas? Alguma fonte trata o assunto de forma mais completa que as outras?"

**Resposta obtida (resumo):** A IA identificou a DigitalOcean como a fonte mais completa (cobre até BCNF, anomalias de dados e a discussão normalização vs. desnormalização), enquanto a freeCodeCamp foi classificada como mais pedagógica (ensino passo a passo com um único exemplo evolutivo). Gerou até uma tabela comparativa cruzando as duas fontes por recurso coberto (1NF/2NF/3NF, BCNF, anomalias, desnormalização).

**Observações:** A IA não só identificou divergência de profundidade entre as fontes, como justificou o porquê — isso mostra que ela está de fato comparando conteúdo, não só resumindo cada uma isoladamente.

---

### Prompt 3 — Aplicação prática (exercícios)
**Prompt usado:**
> "Crie 5 exercícios práticos de SQL sobre os temas das fontes (DDL, DML, DQL e normalização), com dificuldade crescente. Para cada exercício, inclua a resposta esperada."

**Resposta obtida (resumo):** Gerou 5 exercícios em ordem crescente de dificuldade: (1) SELECT básico, (2) CREATE TABLE + INSERT com chave primária, (3) JOIN entre duas tabelas, (4) identificar violação de 1NF e corrigir, (5) identificar dependência transitiva e normalizar até 3NF — cada um com enunciado e resposta esperada.

**Observações:** A progressão de dificuldade fez sentido pedagógico real, do comando mais simples até um caso de normalização mais complexo. Os exercícios de normalização (4 e 5) exigiram raciocínio aplicado, não só memorização de sintaxe.

---

### Prompt 4 — Teste de limite / troubleshooting
**Prompt usado:**
> "Explique o que é uma View em SQL e me dê um exemplo de CREATE VIEW, usando apenas as informações presentes nas fontes carregadas."

**Resposta obtida (resumo):** A IA explicou o conceito de View como camada intermediária/"denormalização" para facilitar BI e otimizar performance, e gerou um exemplo de CREATE VIEW. Porém, como o tema "View" não era detalhado em profundidade em nenhuma fonte isolada, ela precisou **combinar fragmentos de fontes diferentes** para montar o exemplo completo.

**Dificuldade encontrada:** A View não estava documentada como um bloco único e completo em nenhuma fonte — o comando `CREATE VIEW` veio de uma fonte e a sintaxe de `SELECT` de outra. A IA precisou preencher a lacuna da sintaxe de conexão (`AS`) com conhecimento próprio da linguagem SQL.

**Como resolvi:** Não precisei reformular o prompt — o interessante é que a própria IA foi transparente sobre a lacuna: sinalizou explicitamente no texto qual parte veio das fontes e qual parte foi inferência dela para completar a sintaxe. Isso me mostrou, na prática, como avaliar se uma resposta de RAG está "inventando" ou sendo honesta sobre suas limitações.

---

## 📖 Miniguia de Estudo (Entrega Final)

### Resumo Estruturado

**1. DDL — Data Definition Language**
Comandos que definem e modificam a estrutura do banco: `CREATE TABLE` (cria tabelas), `ALTER TABLE` (modifica estrutura existente, como adicionar chaves estrangeiras), `DROP TABLE` (exclui permanentemente), `CREATE DATABASE`/`DROP DATABASE` (criam/removem o banco como um todo) e `CREATE INDEX` (cria índices para acelerar buscas).

**2. DML — Data Manipulation Language**
Comandos que gerenciam os dados dentro das estruturas já criadas: `INSERT INTO` (popula tabelas com novas linhas), `UPDATE` (modifica dados existentes) e `DELETE` (remove registros).

**3. DQL — Data Query Language**
A parte do SQL dedicada à recuperação e análise de dados: `SELECT` (comando base de consulta), `WHERE` (filtra registros), `ORDER BY` (ordena resultados), `JOIN` (combina linhas de tabelas relacionadas — INNER, LEFT, RIGHT, FULL), funções de agregação (`COUNT()`, `SUM()`, `AVG()`, `MIN()`, `MAX()`) e `GROUP BY`/`HAVING` (agrupam e filtram grupos de linhas).

**4. Modelagem Relacional**
Chave Primária (Primary Key) identifica cada linha de forma única em uma tabela. Chave Estrangeira (Foreign Key) estabelece relacionamento entre duas tabelas, apontando para a chave primária de outra.

**5. Normalização**
Processo de organizar tabelas para reduzir redundância e prevenir anomalias de inserção, atualização e exclusão, através das formas normais (1NF, 2NF, 3NF, BCNF). A 1NF exige atomicidade dos valores (nada de múltiplos valores numa mesma célula); a 2NF exige que atributos não-chave dependam da chave primária inteira; a 3NF elimina dependências transitivas (quando um atributo não-chave depende de outro atributo não-chave, e não diretamente da chave primária). Em cenários de alta performance, é possível optar pela desnormalização — abrir mão de parte da normalização em troca de consultas mais rápidas, geralmente via Views.

---

### Glossário

| Termo | Definição |
|---|---|
| DDL | Data Definition Language — comandos que definem a estrutura do banco (CREATE, ALTER, DROP) |
| DML | Data Manipulation Language — comandos que manipulam os dados (INSERT, UPDATE, DELETE) |
| DQL | Data Query Language — comandos de consulta e recuperação de dados (SELECT e cláusulas) |
| Chave Primária (PK) | Coluna que identifica de forma única cada linha de uma tabela |
| Chave Estrangeira (FK) | Campo que estabelece relacionamento entre duas tabelas, apontando para a PK de outra |
| JOIN | Comando que combina linhas de duas ou mais tabelas com base em uma coluna relacionada (INNER, LEFT, RIGHT, FULL) |
| Normalização | Processo de organizar tabelas para reduzir redundância e garantir integridade dos dados |
| 1FN (1NF) | Exige que todos os valores sejam atômicos — nenhuma célula pode conter múltiplos valores |
| 2FN (2NF) | Exige que todo atributo não-chave dependa da chave primária completa (não de parte dela) |
| 3FN (3NF) | Elimina dependências transitivas — atributo não-chave não pode depender de outro atributo não-chave |
| BCNF | Boyce-Codd Normal Form — versão mais estrita da 3NF |
| Anomalias de Dados | Problemas de inserção, atualização ou exclusão causados por dados mal normalizados |
| Desnormalização | Processo inverso à normalização, usado para otimizar performance de leitura em troca de redundância controlada |
| View | Camada intermediária/consulta salva que simplifica o acesso a dados sem alterar as tabelas originais |

---

### Prompts Reutilizáveis para Revisão Futura

Prompts testados e validados, prontos para reaproveitar em futuras sessões de estudo:

```
1. "Resuma os conceitos fundamentais de [tópico] presentes nas fontes, organizando por categorias"
2. "Compare como as fontes definem e explicam [conceito] — há diferenças de profundidade ou abordagem entre elas?"
3. "Crie 5 exercícios práticos sobre [tópico], com dificuldade crescente e resposta esperada"
4. "Explique [conceito específico] usando apenas as informações presentes nas fontes carregadas"
   (útil para testar se a IA está ancorada nas fontes ou completando com conhecimento genérico)
```

---

## 🛠️ Ferramenta utilizada

[NotebookLM (Google)](https://notebooklm.google.com/)

## ✍️ Autor

**Pablo Henrique** — Estudante de Database Technology 
[LinkedIn](https://www.linkedin.com/in/pablo-henrique-barbosa-silva-53a4a1314) | [GitHub](https://github.com/pablohrnq)
