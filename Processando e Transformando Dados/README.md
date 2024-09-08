# Limpeza e transformação dos dados com POWER BI


## Descrição do projeto
 O projeto consiste na criação de uma instância Azure para MySQL, na qual posteriormente será criado um banco de dados denomidado Azure_Company, utilizando para isso os scripts disponibilizado no repositório da [Juliana Zanellatto - power bi analyst - Módulo 3 Desafio de projeto](https://github.com/julianazanelatto/power_bi_analyst/tree/main/M%C3%B3dulo%203/Desafio%20de%20Projeto) . Após a criação do banco de dados deve-se realizar a persistência dos dados e integrar o banco Azure Company com o Power Bi para realizar a transformação dos dados.

 Os scripts de criação do banco de dados e inserção de dados estão disponíveis nos link a seguir: [Script de criação do banco de dados](bit.ly/3wPG4JH) e [Script de dados para ser persistido](https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Script%20SQL/insercao_de_dados_e_queries_sql.sql).

A etapa de transformação dos dados tem como objetivo atender as seguintes premissas:
- Analisar os cabeçalhos e tipos de dados.
- Modificar os valores monetários para o tipo double preciso.
- Verificar a existência dos nulos e analisar a remoção.
- Verificar se há algum colaborador sem gerente.
- Verificar se há algum departamento sem gerente. 
- Verificar o número de horas dos projetos.
- Separar as colunas complexas.
- Mesclar consultas employee e departament para criar uma tabela employee com o nome dos departamentos associados aos colaboradores. 
- Eliminar as colunas desnecessárias.
- Realizar a junção dos colaboradores e respectivos nomes dos gerentes. Isso pode ser feito com consulta SQL ou pela mescla de tabelas com Power BI. 
- Mesclar as colunas de Nome e Sobrenome para ter apenas uma coluna definindo os nomes dos colaboradores.
- Mesclar os nomes de departamentos e localização.
- Explicar por que, neste caso supracitado, podemos apenas utilizar o mesclar e não o atribuir. 
- Agrupar os dados a fim de saber quantos colaboradores existem por gerente.
- Eliminar as colunas desnecessárias, que não serão usadas no relatório, de cada tabela.

O relatório em Power Bi pode ser visualizado por meio link: [Company report](https://app.powerbi.com/view?r=eyJrIjoiMTdkYTVlZDItODZlYy00YTg1LTg4YjUtODgxYWFkOTJhM2JlIiwidCI6IjMxMTU3MGI0LTFhYmMtNGRmZS05NjgzLTFlNGQ4ZDZmOGExNiJ9).

## Banco de dados Azure_Company

A criação da instância do MySQL na Azure, configuração do banco de dados persistência dos dados e integração do Power BI com a Nuvem foi realizada conforme o tutorial de apresentação do projeto.

- Imagem do banco de dados configurado na Azure"
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Imagem.%20BD%20Azure.png">
</div>

- Imagem da seleção do tipo de conexão do banco de dados com o Power BI
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Sele%C3%A7%C3%A3o%20do%20banco%20de%20dados.png">
</div>

- Imagem da configuração do banco de dados no Power BI
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Acesso%20ao%20servidor.png">
</div>
 
- Imagem do carregamento das tabelas do banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Carregamento%20de%20tabelas.png">
</div>


## Tabela Departament

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Renomear tabela|Foi alterado o nome da tabela de azure_company departament para departament|
|Exclusão de colunas|Foi realizada a exclusão das colunas azure_company.dept_loactions, azure_company.employee,azure_company.project|
|Mesclar tabelas|Foi realizada a inclusão da coluna Dlocations da tabela Dept_locations|
|Renomear colunas|Foi realizada a alteração do nome da coluna azure_company dept_locations.Dlocation para D.location
|Mesclar Colunas| Foi realizada a união das colunas Dname com a coluna D.locations gerando uma no coluna|
|Inserir localização do departamento| Foi utilizado a mescla de consultas para associar a cada departamento da consulta departament a localização existente na tabela dept.location. Neste caso foi utilizado a mescla de colunas devido a necessidade de combinar as informações que contemplem o departamento e a localização em uma unica estrutura. Ainda neste cenário não se deve utilizar a ação atribuir de colunas, pois isso apenas adicionar uma nova coluna que deve ser baseada em um cálculo ou experssão DAX. |
| Exclusão de colunas| Exclusão da coluna locations que não será utilizada nos relatórios.|


- Imagem da tabela departament banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Departament.png">
</div>

## Tabela Departament locations

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Renomear tabela|Foi alterado o nome da tabela de azure_company dept_locations para dept_locations|
|Remover colunas|Foi realizada a exclusão da coluna azure_company.departament|

- Imagem da tabela Departament location do banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Departament%20Location.png">
</div>

## Tabela Dependent

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Renomear tabela|Foi alterado o nome da tabela de azure_company dependent para dependent|
|Exclusão de coluna|Foi realizada a exclusão da coluna azure_company.employee|

- Imagem da tabela Dependent do banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Dependent.png">
</div>

## Tabela Employee

O colaborador James Borg não possui um gerente. Este indica que o colaborador James Borg trata-se do Gerente Geral ou diretor na Azure_Company.

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Renomear tabela|Foi alterado o nome da tabela azure_company employee para employee|
|Exclusão de coluna|Foi realizada a exclusão das colunas azure_company.departament, azure_company.employee(Ssn), azure_company.employee(Super_ssn),azure_company.works_on|
|Separa colunas complexas| Foi realizada a divisão da coluna Address em outras três colunas que irão abrigar o Number_Address, Address e state|
|Junção de nomes|Foi mesclado o F.name e o L.name dos colaboradores para cria um unico nome do colaborador denomidado E.name|
|Junção de colaboradores e gerentes|Foi realizada uma meslca na consulta employee para associar a cada colaborador o nome de seu respectivo gerente|
 
 - Imagem da tabela Employee do banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Employee.png">
</div>


## Tabela Project

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Renomear tabela|Foi alterado o nome da tabela azure_company Project para Project|
|Exclusão de coluna| Foi realizada a exclusão das colunas azure_company.departament, azure_company.works_on|

- Imagem da tabela Project do banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Project.png">
</div>

## Tabela Works_on

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Renomear tabela|Foi alterado o nome da tabela azure_company Works_on para Works_on|
|Exclusão de coluna|Foi realizada a exclusão das colunas azure_company.employeet, azure_company.Project|

- Imagem da tabela Works_on do banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Works%20on.png">
</div>

## Tabela Employee-Manager

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Criação da tabela Employee-Manager|A consulta employee foi duplicada para criar uma nova tabela denominada Employee-Manager.|
|Exclusão de colunas|Todas as colunas da consulta Employee-manager foram excluídas com excessão da colunas E.name e N.manager|

- Imagem da tabela Employee-Manager banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Employee_manager.png">
</div>

## Tabela Employee_departament

Relação de Ações de tratamento de dados
|Ação|Descrição|
|----|----------------|
|Criação da tabela Employee_departament| A tabela foi criada a partir da mescla das consultas employee e departament, para relacionar o departamento aos colaboradores|
|Exclusão de colunas| Foi realizada a exclusão de todas as colunas da tabela employee_departament, com exceção das colunas Fname, Lname, Ssn, departament.Dname e Dno|


- Imagem da tabela Employee_departament do banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Employee_departament.png">
</div>

## Criação do relacionamentos entre tabelas

Terminada a etapa de tratamento dos dados do banco de dados Azure-Company, foi relizada a etapa de criação de relacionamento entre as tabelas para possibilitar a elaboração de um relatório com as principais informações. Foi utilizado o modelo estrela na criação dos relacionametos

- Imagem da estrutura de relacionamentos criada
div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Relacionamento.png">
</div>

## Company Report

Utilizando o banco de dados Azure_Company foi elaborado o Company report com a principais informações persistidas na base de dados. O Company report está disponível para interação por meio link [Company Report](https://app.powerbi.com/view?r=eyJrIjoiMTdkYTVlZDItODZlYy00YTg1LTg4YjUtODgxYWFkOTJhM2JlIiwidCI6IjMxMTU3MGI0LTFhYmMtNGRmZS05NjgzLTFlNGQ4ZDZmOGExNiJ9)

- Imagem da tabela departament banco de dados Azure_Company
<div aling="center">
 <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Company%20report.png">
</div>

## Autores

- [Frederico S N Cota](https://github.com/Sanderfn)