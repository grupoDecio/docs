# Documentação das Tabelas do Banco de Dados do Fluig

> Baseado no conteúdo de [WSA - Tabelas do Banco de Dados do Fluig](https://www.wsa.com.br/tabelas-do-banco-de-dados-do-fluig/)

## Introdução

Esta documentação descreve as principais tabelas disponíveis no banco de dados do Fluig. As tabelas são utilizadas para armazenar informações sobre processos, workflows, anexos, documentos, e outras entidades relevantes dentro do sistema Fluig.

## Tabelas do Banco de Dados

### 1. DEF_PROCES

**Descrição:** Definição do processo como um todo, ou seja, o processo em si, desconsiderando sua versão.

### 2. VERS_DEF_PROCES

**Descrição:** Versão do processo e suas variáveis que são versões a cada liberação.

### 3. PROCES_WORKFLOW

**Descrição:** Refere-se a uma solicitação como um todo.

### 4. ANEXO_PROCES

**Descrição:** Anexos do processo (considere o próprio formulário atrelado).

### 5. DOCUMENTO

**Descrição:** Documentos atrelados no Fluig via GED ou não. Formulários e registros de formulários também são considerados documentos.

### 6. METALISTA

**Descrição:** Toda tabela que começa com ML é uma metalista, ou seja, uma tabela criada automaticamente através da importação de um formulário sem fluir para ser persistido.

As tabelas são criadas em ordem, na medida que os formulários são criados e são estruturados da seguinte forma.

**ML AAA BBB**

Onde ML é o prefixo para meta_lista no fluig, enquanto AAA é o código da empresa e BBB é a numeração sequencial gerada pelo próprio fluig.

Aqui são alguns exemplos de nomes dessas tabelas criadas no fluig: ML001001, ML002050

### 7. HISTOR_PROCES

**Descrição:** Tabela que guarda o histórico de movimentações de uma solicitação.

### 8. TAR_PROCES

**Descrição:** Tabela que guarda os dados de uma atividade em geral, sendo completamente atrelada a um HISTOR_PROCES.

### 9. TAR_WORKFLOW

**Descrição:** Tabela composta que é um objeto de TAR_PROCES a TAR_CTRAL.

### 10. TAR_CTRAL

**Descrição:** Tabela que compõe um registro na central de tarefas. Pode ser referente a outros tipos de atividades também, como aprovação de documentos.

### 11. ADHOC_PROCES

**Descrição:** Tabela atrelada a PROCES_WORKFLOW que guarda informações de uma solicitação AD_HOC.

### 12. ADHOC_PROCES_WORKFLOW

**Descrição:** Guarda informações das tarefas de um ADHOC.

### 13. ESTADO_PROCES

**Descrição:** Tabela que guarda informações das tarefas de um processo.

### 14. EVENT_PROCES

**Descrição:** Tabela que guarda informações do Fluig quanto a eventos que podem ser disparados durante uma movimentação.

### 15. EVENT_FICHA

**Descrição:** Tabela do banco de dados do fluig que armazena os eventos de formulário do fluig.

### 16. FDN_USER_TENANT

**Descrição:** Representação ativa do usuário, uma coluna USER_CODE, sua própria matriz, utilizada como chave para várias outras tabelas, incluindo TAR_PROCES.

### 17. PROCESS_OBSERVATION

**Descrição:** Comentários dos processos do Fluig.

### 18. FICHARIO

**Descrição:** Esta tabela controla a estrutura principal e a estrutura PAI X Filho dos formulários.

### 19. FICHARIO_CAMPO

**Descrição:** Esta tabela controla quais campos cada versão de um formulário possui.

### 20. SERV_DATASET

**Descrição:** Tabela do Fluig que lista os datasets internos e datasets customizados.

## Considerações Finais

As tabelas descritas acima são fundamentais para o funcionamento do Fluig, armazenando dados críticos para a gestão de processos, documentos, tarefas e eventos. O conhecimento detalhado de cada tabela e suas interrelações é essencial para administradores e desenvolvedores que trabalham com o banco de dados do Fluig.
