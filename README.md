# Desafio-Processamento-de-Dados-Simplificado-com-Power-BI

Desafio Processamento de Dados Simplificado com Power BI

1. Criação de uma instância na Azure para MySQL
2. Criar o Banco de dados com base disponível no github
3. Integração do Power BI com MySQL no Azure
4. Verificar problemas na base a fim de realizar a transformação dos dados
Os dados foram tratados no SQL

Diretrizes para transformação dos dados

1. Verifique os cabeçalhos e tipos de dados
Como os dados já foram tratados no Banco, não tem problema de cabeçalho

2. Modifique os valores monetários para o tipo double preciso

3. Verifique a existência dos nulos e analise a remoção
Constatado que tem valor nulo de gerente. Não pode ser removido porque ficaria faltando colaborador no relatório. O próprio

4. Os employees com nulos em Super_ssn podem ser os gerentes. Verifique se há algum colaborador sem gerente
Sim. Há colaborador sem gerente

5. Verifique se há algum departamento sem gerente
São 3 departamentos e todos tem gerentes

6. Se houver departamento sem gerente, suponha que você possui os dados e preencha as lacunas
Foi tratado na base mas não constatei falta de gerente

7. Verifique o número de horas dos projetos

8. Separar colunas complexas
Colunas separadas (são as colunas que vem por causa das constraints no banco de dados

9. Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. A mescla terá como base a tabela employee. Fique atento, essa informação influencia no tipo de junção

10. Neste processo elimine as colunas desnecessárias.
Ok, Colunas que não serão utilizadas no relatório foram eliminadas (Foi pego apenas Nome do Departamento da tabela departamento)

11. Realize a junção dos colaboradores e respectivos nomes dos gerentes . Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. Caso utilize SQL, especifique no README a query utilizada no processo.


12. Mescle as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores
Ok. Coluna nomeada para Nome Completo

13. Mescle os nomes de departamentos e localização. Isso fará que cada combinação departamento-local seja único. Isso irá auxiliar na criação do modelo estrela em um módulo futuro.
14. Explique por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir.
Porque este processo é como se fosse um inner/left join entre tabelas para pegar os dados relacionados. Já atribuir, seria uma insersão dos valores de uma tabela em outra.
15. Agrupe os dados a fim de saber quantos colaboradores existem por gerente
16. Elimine as colunas desnecessárias, que não serão usadas no relatório, de cada tabela

Observação:
Constatei que existem várias localizações para o mesmo departamento (dept_locations), ou seja, há três localizações diferentes para Dnumber = 5 o que acaba gerando duplicidade de informações quando é feito o relacionamento das tabelas.
Eliminei as duas últimas localizações.
