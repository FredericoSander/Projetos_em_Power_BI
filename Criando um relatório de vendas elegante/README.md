# Criando um relatório de venda elegante com Power BI

Neste desafio de projeto, foi criado um relatório em Power Bi com 3 páginas para apresentar os resultados das vendas de uma empresa fictícia realizadas entre setembro de 2013 e dezembro de 2014. Nesta base de dados, são apresentadas as seguintes informações:
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

Por meio destes dados forma elaborado 3 paineis para apresentação de análise para tomada de decisão. O relatório encontra-se disponível para interação por meio do link [Criando um relatório de venda elegante com Power BI.](https://bit.ly/DesafiodeProjetoDIO)

No desenvolvimento do projeto foi solicitado o atendimento aos seguinte requisitos.
- Manter a estrutura definida.
- Implementar os botões de navegação que fornecem navegabilidade.
- Utilizar segmentadores com imagnes associadas.
- Utilizar os indicadores e botões para selecionar diferentes visuais sobre o mesmo assunto.
- Criar a segunda página do relatório.
- Publicar o relatório no Power Bi Service.
- Possibilidade de criação de outros elementos e artifícios conforme familiaridade.
- Entregar projeto via link do GitHub.


## Painel 1 - Sales Report

O painel Sales Report foi desenvolvido em conjunto com a instrutura Juliana Mascarenha durante a apresentação do desafio. Entretanto, foram realizadas algumas alterações em relação ao conteúdo apresentado pela instrutora.
- Foi retirada a seta de mudança de pagina e incluídos ícones caracterizando as demais paginas.

<div aling="center">
 <img src="https://github.com/Sanderfn/PowerBIAnalyst-Projeto1/blob/main/Paineis/Imagem%201%20-%20Sales%20Report.png">
</div>>

No Painel 1 - Sales Report, são apresentados 5 cartões e 4 gráficos com dados consolidado de acordo com o período selecionados, apresentando os seguintes indicadores.
- Cartões:
    - Total de vendas: Somatório dos valores liquidos das vendas.
    - Total de unidades Vendidas: Somatório da quantidade de unidades vendidas.
    - Valor total de descontos: Somatório dos valores concedidos como descontos.
    - Lucro total: Somatório do lucro de cada venda realizada.
    - Custo total das vendas: Somatório do custo de cada venda realizada.
- Gráficos:
    - Total das vendas por mês: Apresenta o valor total das vendas realizadas em seus respectivos meses dos ano, de acordo com o intervalo de data selecionado.
    - Vendas por segmento: Apresenta o valor total das vendas realizadas conforme o segmento de mercado de atendimento de acordo com o intervalo de data selecionado. Este gráfico apresenta 2 visuais para a mesma informação sendo disponibilizado um gráfico de Bar chart ou um Pie chart, que são alternados pela seleção dos botões.
    - Vendas por produto: Apresenta o valor total das vendas realizadas por produto comercializado de acordo com o intervalo de data selecionado.
    - Vendas por país: Apresenta o valor total das vendas realizadas em cada país de atendimento de acordo com o intervalo de data selecionado. Este gráfico apresenta 2 visuais para a mesma informação sendo disponibilizado um gráfico de map chart ou um Treemap chart, que são alternados pela seleção dos botões.

Foram utilizados 3 icones para navegação nas paginas do relatório.

- O ícone <img src="https://github.com/Sanderfn/PowerBIAnalyst-Projeto1/blob/main/Icones/lucro.jpg" width="20"/> disponivel na barra lateral das paginas Sales Report e Product Report direciona o usuário para a pagina de **Profit Report**.

- O ícone <img src="https://github.com/Sanderfn/PowerBIAnalyst-Projeto1/blob/main/Icones/vendas.png" width="20"/> disponivel na barra lateral das paginas Sales Report e Profit Report direciona o usuário para a pagina de **Product Report**.

- Já o ícone <img src="https://github.com/Sanderfn/PowerBIAnalyst-Projeto1/blob/main/Icones/Acordo%20fechado.png" width="20"/> disponivel na barra lateral das paginas Profit Report e Product Report direciona o usuário para a pagina de **Sales Report**.

## Painel 2 - Profit Report

O Painel Profit Report foi desenvolvido a partir do modelo apresentado. Entretanto, toda a estrutura de análise dos dados e formatação dos gráficos foram deixadas para o aluno desenvolver como parte do desafio.

O relatório Profit Report tem por finalidade detalhar o lucro obtido por meio das operações de comercialização dos produtos demonstrando os resultados por produto, país, segmento e ano das operações.

<div aling="center">
<img src="https://github.com/Sanderfn/PowerBIAnalyst-Projeto1/blob/main/Paineis/Imagem%202%20-%20Profit%20Report.png">
</div>

No Painel 2 - Profit Report, são apresentados 4 gráficos com dados consolidado que pode ter seu intervalo de análise modificado por ano de exercício, apresentando os seguintes indicadores.

- Gráficos:
    - Distribuição do lucro por ano e país: Este gráfico de árvore hierárquica apresenta o valor da soma do lucro detalhando sequencialmente a fração do lucro correspondente a cada ano da base de dados e descrevendo o lucro auferido em cada país no ano selecionado.
    - Lucro por produto: Este gráfico de radar apresenta o valor do lucro auferido para com cada produto do protifólio em cada respectivo ano. 
    - Lucro por segmento: Este gráfico de barras clusterizados apresenta o valor do lucro auferido em cada segmento de atuação para cada ano selecionado.
    - Distribuição do lucro por trimestre: Este gráfico de cascata apresenta a distribuição do lucro por trimestre e o acumulado anual. 
-Filtro:
    - Ano: Este filtro tem por finalidade limitar o período de análise por ano.
      
## Painel 3 - Product Report

O Painel Product Report foi desenvolvido a partir do conhecimento desenvolvido durante os cursos apresentados e entre outras referencias consultadas, com o proposito de desenvolver novas habilidades de capacidade de analitica indispensáveis ao mercado de trabalho. Foi utilizado como base o mesmo Layout e gráficos construidos anteriormente que se mostraram coerentes ao proposito da apresentação. 

<div aling="center">
<img src="https://github.com/Sanderfn/PowerBIAnalyst-Projeto1/blob/main/Paineis/Imagem%203%20-%20Product%20Report.png">
</div>

No Painel 3 - Product Report, são apresentados 4 gráficos com dados consolidado que pode ter seu intervalo de análise modificado por ano de exercício. Os gráficos apresentam os resultados para cada produto descrito na base de dados detalhando seu desempenho de vendas por país, segmento, trimestre a acumulado do ano. Os gráficos deste relatório possuem os títulos dinâmicos que se adequam a cenário análisado. Neste relatório são apresentados os seguintes indicadores.

- Gráficos:
    - Distribuição do produto por país e segmento: Este gráfico de árvore hierárquica apresenta o valor da soma das unidades vendidas detalhando sequencialmente a fração das unidades correspondente a cada país da venda e descrevendo a quantidade de venda por segmento no país selecionado.
    - Lucro unitário do produto por país: Este gráfico de barras apresenta o valor do lucro unitário auferido para com cada produto do protifólio em cada pais de comercialização e no respectivo ano de referencia. 
    - Percentual de desconto do produto por país: Este gráfico de barras clusterizados apresenta o percentual de desconto que foram concedidos em cada país para o produto e o ano selecionado.
    - Quantidade de unidades vendidas: Este gráfico de cascata apresenta a distribuição da unidade do produto vendidas por trimestre e o acumulado anual das vendas. 
- Filtros:
    - Ano de referência: Este filtro tem por finalidade limitar o período de análise em um ano.
    - Descrição do produto: Este filtro tem por finalidade limita a análise a apenas um produto por vez, permitindo a analise do desempenho deste produto nos diferentes países e mercado de comercialização.