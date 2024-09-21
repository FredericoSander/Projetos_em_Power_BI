# Criando um Modelo Star Schema 
# Descrição do projeto

<p align="justify"> 
Este desafio de projeto teve como objetivo o desenvolver habilidades de criação de modelos Star Schema, essenciais para melhorar o desempenho no Power Bi. O Power BI oferece uma performance otimizada ao trabalhar com dados modelados neste formato. Para a criação do modelo Star Schema, foi fornecido um modelo de banco de dados relacional para servir de referência para adequações necessarias a estrutura final.
</p>
## Modelo relacional
<p align="justify"> 
 O **modelo de dados relacional** é amplamente utilizado na atualidade, sendo um dos mais populares dentre os diversos modelos existentes. Ele oferece uma maneira intuitiva e direta de representar os dados em tabelas. Em um modelo relacional cada linha em uma tabela é um registro com uma ID exclusiva (Chave Primária). As tabela, por sua vez, são compostas por colunas  que armazenam os atributos dos dados persistidos.
 O modelo de relacional é empregado por organizaões de diversos portes e segmentos, atendendo a uma vasta gama de aplicações, desde o controle de vendas diarias de grandes redes até a gestão de processos operacionais de produção. Os banco de dados relacionais ideais para cenários em que os dados precisam se relacionar e ser gerenciados de forma segura e consistente, com base em regras definidas.
</p>

 - Imagem do modelo relacional fornecido
<div aling="center">
 <img src="https://github.com/FredericoSander/Power-BI/blob/main/Criando%20um%20Star%20Schema/Imagens/Modelo%20de%20refer%C3%AAncia.png">
</div>

## Modelo Star Schema 
<p align="justify"> 
 O modelo Star Schema, trata-se um modelo maduro e amplamente utilizado por Data Warehouses relacionais. Ele requer que os modeladores classifiquem suas tabelas de modelo como dimensão ou fato.

 **Tabelas dimensões**: Nessa tabela são descritos as entidades de negocio, essas entidades podem incluir produtos, pessoas, locais e conceitos, incluindo o próprio tempo. A tabela mais consistente que existirá neste modelo é a tabela Data. Uma tabela Dimensão contém uma ou mais colunas de chaves, que atua como identificadores exclusivos e colunas descritivas.

 **Tabelas Fatos**: Nessa tabela são armazenados os eventos ou observações que podem ser ordens de vendas, saldos de ações, taxas de câmbio, temperaturas, etc. Uma tabela contém colunas chaves de dimensão relacionadas as tabelas de dimensões e colunas de medidas númericas. As colunas de chave de dimensão determinam a dimensionalidade de uma tabela de fatos, enquento os valores de chave de dimensão determinam a granularidade da tabela fatos. As tabelas fatos diferente mente das tabela de dimensão possuem um numero relativamente grande de linhas que crescem ao longo do tempo.
</P>

 - Imagem do modelo Star Schema desenvolvido
<div aling="center">
 <img src="https://github.com/FredericoSander/Power-BI/blob/main/Criando%20um%20Star%20Schema/Imagens/Modelo%20StarSchema.png">
</div>

### Tabelas Fato
<p align="justify"> 
**Tabela F_Teacher**: 
A tabela F_Teacher é a tabela fato, onde serão cadastradas as informações relacionadas aos professores. Nela, são cadastrados os cursos mininstrados pelos professores, bem como as datas de inicio e termino de cursos e disciplinas associados. Essas informações são vinculadas através de chaves estrangeiras que realacionam  com as chaves  primárias por meio das tabelas de dimensão. A tabela F-Teacher possui um relacionamento de **um para muitos** com todas as tabela dimensão, refletindo o vinculo entre professores as atividade ao longo do tempo. Esta tabela apresenta um crescimento temporal a partir do cadastro de novas atividades.

### Tabelas Dimensão

**Tabela D_Teacher**: A tabela D_Teacher trata-se de uma tabela dimensão que será utilizada para o cadastro dos professores. Dentre as informações cadastradas estão:

- **Name**: Nesta coluna são armazenadas as informações do nome dos professores.
- **Last_Name**: Nesta coluna são armazenadas as informações do último nome dos professores.
- **CPF**: Nesta coluna são armazenados as informações de CPF dos professores cadastrados.
- **Phone_Number**: Nesta coluna são armazenados as informações do número de telefone utilizados para contato.
- **E-mail**:  Nesta coluna são armazenados as informações de e-mail dos professores.

Esta tabela é destinada a armazenar as informações básicas, servindo de base para consultas com foco nos professores da instituição.

**Tabela D_Course**: A tabela D_Course trata-se de uma tabela dimensão que será utilizada para o cadastro dos cursos. Dentre as informações cadastradas estão:

- **Cod**: Esta coluna é destinada ao armazenamento do código do curso que deve ser exclusivo para cada curso. Embora este código possa ser utilizado como chave primária devido a sua exclusividade, o mesmo é utilizado apenas para consultas.
- **Name**: Esta coluna é destinada ao armazenamento do nome dos cursos.
- **Syllabus**: Esta coluna é destinada ao armazenamento dos conteúdos programáticos.
- **WorkLoad**: Nesta coluna é armazenada a carga horária de cada curso.
- **Credits**:  Nesta coluna são armazenadas informações os créditos de cada curso.
- **Create_Date**: Esta coluna é destinada ao armazenamento da data de criação dos cursos.
- **Shutdown_Date**:  Esta coluna é destinada ao armazenamento da data de encerramento dos cursos.

 Esta tabela é destinada a armazenar as informações básicas dos cursos, servindo de base para consultas dos cursos da instituição. 

**Tabela D_Departament**: A Tabela D_Departament trata-se de uma tabela dimensão que será utilizada para o cadastro dos despartamentos da isntituição. Dentre as informações cadastradas estão:

- **Cod_Departament**: Esta coluna é destinada ao armazenamento do código dos departamentos que deve ser exclusivo para cada disciplina. Embora possa ser utilizado como chave primária devido a sua exclusividade, o mesmo é utilizado apenas para consultas.
- **Name**: Esta coluna é destinada ao armazenamento do nome dos departamentos da instituição.
- **Description**: Esta coluna é destinada ao armazenamento das informações referente as atividades dos departamentos.
- **Create_Date**: Esta coluna é destinada a data de criação dos departamentos.
- **Shutdown_Date**:  Esta coluna é destinada a data de fechamento dos departamentos.

 Esta tabela é destinada a armazenar as informações básicas do departamentos, servindo de base para consultas com foco nos departamento da instituição. 

**Tabela D_Discipline**: A tabela D_Discipline é uma tabela dimensão utilizada para o cadastro das disciplinas. Dentre as informações cadastradas estão:

- **Cod_Discipline**: Esta coluna é destinada ao armazenamento do código das disciplinas que deve ser exclusivo para cada disciplina. Embora possa ser utilizado como chave primária devido a sua exclusividade, o mesmo é utilizado apenas para consultas.
- **Name**: Esta coluna é destinada ao armazenamento do nome das disciplinas.
- **Syllabus**: Esta coluna é destinada ao armazenamento do conteúdo programático das disciplinas.
- **WorkLoad**: Nesta coluna é armazenada a carga horária de cada disciplina.
- **Credits**:  Nesta coluna são armazenadas os créditos de cada disciplina cadastrada.
- **Create_Date**: Esta coluna é destinada ao armazenamento da data de criação das disciplinas.
- **Shutdown_Date**:  Esta coluna é destinada ao armazenamento da data de encerramento das disciplinas.

Esta tabela é destinada a armazenar as informações básicas das disciplinas, servindo de base para consultas com foco nas disciplinas da instituição. 
</p>

## Autor

- [Frederico S N Cota](https://github.com/Sanderfn)