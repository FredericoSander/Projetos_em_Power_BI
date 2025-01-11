# Processando e Transformando Dados com Power BI

## Índice 

* [Processando e Transformando Dados com Power BI](#processando-e-transformando-dados-com-power-bi)
* [Índice](#índice)
* [Descrição do Projeto](#descrição-do-projeto)
* [Criação do banco de dados na Azure](#criação-do-banco-de-dados-na-azure)
* [Criação das tabelas](#criação-das-tabelas)
* [Relacionamentos](#relacionamentos)
* [Técnicas e tecnologias utilizadas](#técnicas-e-tecnologias-utilizadas)
* [Conclusão](#conclusão)
* [Status do Projeto](#status-do-projeto)
* [Acesse o Projeto](#acesse-o-projeto)


## Descrição do Projeto
O projeto consiste na criação de uma instância MySQL na plataforma Azure, onde foi configurado o banco de dados denominado **Azure_Company**. A partir da criação desse banco de dados, dados como informações de funcionários, departamentos e projetos foram inseridos no banco. Posteriormente, esses dados foram integrados ao Power BI através da conexão com o banco de dados MySQL. Durante o processo de integração, foi realizada uma seleção cuidadosa das tabelas a serem carregadas, seguidos por ajustes nos tipos de dados e aplicação de filtros para garantir que as informações fossem apresentadas de forma clara e consistente no relatório final. Os scripts utilizados para essa etapa estão disponíveis nos seguintes links:

- [Script de Criação do Banco de Dados](bit.ly/3wPG4JH): Este script cria todas as tabelas necessárias no banco de dados **Azure_Company**, incluindo tabelas de funcionários, departamentos e projetos, além de definir suas chaves primárias e estrangeiras.
- [Script de Inserção de Dados](https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Script%20SQL/insercao_de_dados_e_queries_sql.sql)

A etapa de transformação dos dados teve como objetivo atender as seguintes premissas:
- Análise de cabeçalhos e tipos de dados.
- Modificação de valores monetários para o tipo **double**.
- Verificação de dados nulos e tratamento de remoção.
- Análise de colaboradores sem gerente e departamentos sem gerente.
- Ajuste nas colunas de horas de projeto.
- Mescla de tabelas e colunas complexas.
- Criação de tabelas derivadas, como **Employee-Manager** e **Employee_Departament**.
- Exclusão de colunas desnecessárias.

O relatório final em Power BI pode ser acessado pelo seguinte link: [Company Report](https://app.powerbi.com/view?r=eyJrIjoiMTdkYTVlZDItODZlYy00YTg1LTg4YjUtODgxYWFkOTJhM2JlIiwidCI6IjMxMTU3MGI0LTFhYmMtNGRmZS05NjgzLTFlNGQ4ZDZmOGExNiJ9).

---

## Criação do banco de dados na Azure

A criação da instância MySQL na Azure, a configuração do banco de dados, a persistência de dados e a integração com o Power BI foram realizadas conforme o tutorial de apresentação do projeto. Abaixo estão as imagens que ilustram essas etapas:

- **Imagem do banco de dados configurado na Azure**
  <div align="center">
    <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Imagem.%20BD%20Azure.png">
  </div>

- **Imagem da seleção do tipo de conexão do banco de dados com o Power BI**
  <div align="center">
    <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Sele%C3%A7%C3%A3o%20do%20banco%20de%20dados.png">
  </div>

- **Imagem da configuração do banco de dados no Power BI**
  <div align="center">
    <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Acesso%20ao%20servidor.png">
  </div>

- **Imagem do carregamento das tabelas do banco de dados Azure_Company**
  <div align="center">
    <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Carregamento%20de%20tabelas.png">
  </div>

---

## Detalhamento das Tabelas e Ações de Tratamento

### Tabela Department

| Ação               | Descrição                                                                                 |
|----------------------|---------------------------------------------------------------------------------------------|
| Renomear Tabela      | O nome da tabela foi alterado para **department**.                                            |
| Exclusão de Colunas  | Colunas desnecessárias foram excluídas, como **dept_locations** e **project**.              |
| Mesclar Tabelas      | A coluna **Dlocations** foi mesclada à tabela **department**.                                 |
| Renomear Colunas     | A coluna **Dlocation** foi renomeada para **Department Location**.                            |
| Mesclar Colunas      | As colunas **Dname** e **Dlocations** foram combinadas.                                       |

O propósito da tabela **Department** é armazenar informações sobre os departamentos da empresa, incluindo seu nome, localidade e gerente responsável. Essa tabela está relacionada à tabela **Employee**, permitindo que se identifique os funcionários que fazem parte de cada departamento e quais departamentos estão atualmente sem gerente atribuído. Essa relação é crucial para análises que envolvem a estrutura organizacional e a gestão de recursos humanos.

Imagem da tabela Department:
<div align="center">
  <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Departament.png">
</div>

### Tabela Employee

| Ação                  | Descrição                                                                 |
|-----------------------|-----------------------------------------------------------------|
| Renomear Tabela       | Alterado para **employee**.                                      |
| Exclusão de Colunas   | Colunas como **Super_ssn** foram removidas.                     |
| Separação de Colunas | Endereços foram divididos em **Number_Address**, **Address** e **State**. |
| Junção de Nomes      | Colunas **F.name** e **L.name** foram combinadas em **E.name**. |

Imagem da tabela Employee:
<div align="center">
  <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Employee.png">
</div>

### Tabela Employee-Manager

| Ação                | Descrição                                          |
|---------------------|--------------------------------------------------|
| Criação de Tabela | Criada a partir da consulta **employee** duplicada. |
| Exclusão de Colunas | Apenas as colunas **E.name** e **N.manager** foram mantidas. |

Imagem da tabela Employee-Manager:
<div align="center">
  <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Employee_manager.png">
</div>

---

## Criação dos Relacionamentos entre Tabelas

Após o tratamento dos dados, foram criados os relacionamentos entre as tabelas para possibilitar análises detalhadas no Power BI. Por exemplo, ao relacionar as tabelas **Employee** e **Department**, é possível calcular o total de colaboradores por departamento, identificar quais departamentos estão sem gerente atribuído e monitorar a alocação de funcionários em projetos específicos. Essa análise pode auxiliar a empresa a melhorar sua gestão de recursos humanos e alocar pessoal de maneira mais eficiente. Esses relacionamentos são fundamentais para garantir a integridade dos dados e facilitar as consultas e relatórios.

Imagem dos Relacionamentos:
<div align="center">
  <img src="https://github.com/Sanderfn/PythonDataAnalytics-Processando-e-Tranformando-Dados-com-Power-BI/blob/main/Imagens/Relacionamento.png">
</div>

---

## Técnicas e tecnologias utilizadas

- ``SQL``
- ``MySQL WorkBench 8.0``
- ``Azure``
- ``Power BI``
- ``Git``
- ``GitHub``

## Considerações Finais
Este projeto demonstrou como integrar um banco de dados MySQL hospedado na Azure ao Power BI e aplicar transformações essenciais para criar relatórios eficazes. Durante o processo, enfrentamos desafios como inconsistências nos dados importados e a necessidade de tratar valores ausentes e formatos de dados inadequados. Esses desafios foram superados por meio de etapas de limpeza, conversão de tipos e criação de tabelas derivadas para garantir a integridade e qualidade das análises realizadas. A etapa de transformação de dados abordou boas práticas de renomeação, mescla e remoção de colunas desnecessárias, garantindo um dataset limpo e eficiente para análise.

## Status do Projeto

![Status do Projeto](http://img.shields.io/static/v1?label=STATUS&message=Concluído&color=GREEN&style=for-the-badge)

## Acesse o Projeto

Você pode acessar o projeto clicando [aqui](https://github.com/FredericoSander/Construa-Banco-de-Dados-do-Zero-SQL/tree/main/Projeto)

## Autor    

| [<img loading="lazy" src="https://avatars.githubusercontent.com/u/136928502?s=96&v=4" width=115><br><sub>Frederico Sander</sub>](https://github.com/FredericoSander)
| :---: | 