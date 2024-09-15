# Modelando um Dashboard de E-commerce com Power BI Utilizando Fórmulas DAX

## Descrição do projeto

Neste desafio de projeto, foi criando um modelo de dados baseado em Star Schema utilizando a tabela Financial Samples como base para a criação das tabelas fato e dimensão. A tabela Financial Sample apresentada as seguintes informações:
- Segmento de vendas.
- País das vendas.
- Produto vendido.
- Faixa de desconto.
- Unidades vendidas.
- Preço de fabricação.
- Preço de venda.
- Vendas brutas.
- Valor do desconto.
- Valor das vendas.
- Custo dos produtos vendidos.
- Lucro e data da vendas.

A tabela Financial Sample Utilizada no projeto pode ser baixada na pasta base de dados acessada pelo Link()

## Modelo Star Schema 


 O modelo Star Schema, trata-se um modelo maduro e amplamente utilizado por Data Warehouses relaccionais. Ele requer que os modeladores classifiquem suas tabelas de modelo como dimensão ou fato.

 **Tabelas dimensões**: Nessa tabela são descritos as entidades de negocio, essas entidades podem incluir produtos, pessoas, locais e conceitos, incluindo o próprio tempo. A tabela mais consistente que existirá neste modelo é a tabela Data. Uma tabela Dimensão contém uma ou mais colunas de chaves, que atua como identificadores exclusivos e colunas descritivas.

 **Tabelas Fatos**: Nessa tabela são armazenados os eventos ou observações que podem ser ordens de vendas, saldos de ações, taxas de câmbio, temperaturas, etc. Uma tabela contém colunas chaves de dimensão relacionadas as tabelas de dimensões e colunas de medidas númericas. As colunas de chave de dimensão determinam a dimensionalidade de uma tabela de fatos, enquento os valores de chave de dimensão determinam a granularidade da tabela fatos. As tabelas fatos diferente mente das tabela de dimensão possuem um numero relativamente grande de linhas que crescem ao longo do tempo.

A construção do modelo Star Schema baseou-se na tabela Financial Sample> Durante a criação do modelo a tabela Financial Sample foi duplicada para dar origem a  3 tabelas dimessão e uma tabela fato. As tabela de dimensão criadas foram D_Product, D_Product_Details, D-Discounts, já a tabela fato criada foi a F_Sales. Além das tabelas Dimenssão e Fatos criadas a partir da Financial Sample foi criada a tabela dimensão dCalendar.


## Autor

- [Frederico S N Cota](https://github.com/Sanderfn)