
# DATASET: Genérico

Em grande parte dos processos desenvolvidos dentro da plataforma do Fluig, observamos que entre processos, os clientes frequentemente demandam pela criação de inúmeras tabelas para fornecerem campos de seleção para um unico input.

Exemplo:

**ds_despesas →** Utilizado no Processo: 10-DESPESAS <br/>
**Campo**: Atendente <br/>
**ID**: atendente


|    ID    |   NOME   |
|----------|----------|
| 1  | Ana Paula Costa Moreira  |
| 2  | André Coimbra  |
| ...  | ...  |


**ds_CategoriaDespesa** → Utilizado no Processo: 10-DESPESAS <br/>
**Campo**: Categoria <br/>
**ID**: zCategoriaDespesa


|    ID    |   NOME   |
|----------|----------|
| 1  | Nota Fiscal de Serviço  |
| 2  | Folha  |
| 3  | Beneficios  |
| ...  | ...  |

# ds_generico

Com o Dataset Genérico, pretendemos resolver essa grande quantidade de datasets redundantes que são meramente um select utilizando um campo zoom

| PROCESSO-CAMPO | OPÇÃO | EXTRA |
|----------|----------|----------|
| 10-DESPESAS-atendente  | Ana Paula Costa Moreira  | null  |
| 10-DESPESAS-atendente  | André Coimbra  | null  |
| 10-DESPESAS-zCategoriaDespesa  | Nota Fiscal de Serviço  | null  |
| 10-DESPESAS-zCategoriaDespesa  | Folha  | null  |
| 10-DESPESAS-zCategoriaDespesa  | Benefícios  | null  |
| 03-CADASRO-zSegmento  | Administrativo | null  |
| 03-CADASRO-zSegmento  | Cadastro/Analise de Crédito | null  |
