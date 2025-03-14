# ProjetodeVendas

Sejam bem-vindos! 

Este é um projeto inicial em ciência de dados, onde o objetivo é simplesmente fazer uma análise de um banco de dados de venda e testar algumas técnicas. 

Bibliotecas: 
-Pandas
-Scikit-learn
-Matplotlib
-Scipy

O que foi feito:

1) Importação do arquivo utilizando pandas. 
2) Verificando quais features a base possui e quais os tipos de dados.
3) Separando um dataframe específico (datadepedido, produtos, pedidos, preçounitario).

Pré-processamento:

4) Verificamos se a base possuía dados faltantes, nulos ou inconsistentes. 
5) Alteramos o tipo da feature 'OrderDate' que estava no formato int64 para datatime.
6) Busquei fazer uma normalização na feature 'QUANTITYORDERED'. 
7) Fiz uma análise estatística da feature 'PRICEEACH' calculando métricas simples: mediana, moda, media, desvio padrão. 

Visualização:

8) O objetivo foi criar um gráfico de barra onde x são os produtos e y é a quantidade total vendida por produto. 
9) Fizemos um groupby de 'PRODUCTLINE' e 'QUANTITYORDERED' e somamos os resultado. Desse modo, conseguimos a quantidade total por produto. 
10) Usamos o matplotlib para plotar o gráfico. 
11) Observamos que 'Classic Cars' foi o mais vendido, em seguida do 'Vintage Cars'.

Análise:

12) Criei uma feacture binária 'Alta_Venda' que é 1 se a quantidadevendida > média e 0 caso contrário.
13) Usando o sklearn utilizamos machine learning para treinar um modelo de predição utilizando o k-NN, com k=5.
As entradas foram quantidadedepedidos e preçoporunidade, e pedimos para ele prever se será ou não alta venda. 
Normalizamos os dados.
14) Verificamos a sua matriz de confusão para olhar as métricas de precisão, recall e f1-score.
15) Usamos K-means para agrupar os produtos com base em quantidade e preço.
16) Plotamos um gráfico com a técnica do Cotovelo para definir um parâmetro k satisfatório, e descobrimos k=3.
17) Fizemos uma análise dos clusters, analisando quais semelhanças os produtos tem e pq foram criandos dessa forma.
18) Listamos os produtos de cada cluster.
19) Analisamos que: 
Cluster 0: Este cluster é dominado por Classic Cars e Vintage Cars, que são produtos de nicho e provavelmente têm um apelo emocional ou colecionável. A quantidade média de pedidos é baixa, o que sugere que esses produtos não são comprados em grandes volumes, possivelmente devido ao seu público-alvo específico.

Cluster 1: Este cluster é fortemente dominado por Classic Cars e Vintage Cars, mas com uma presença significativa de Trucks and Buses e Motorcycles. A quantidade média de pedidos é semelhante ao Cluster 0, mas o preço médio por unidade é significativamente mais alto. Isso sugere que os produtos neste cluster são itens premium ou de alto valor, como modelos raros ou edições especiais de carros clássicos e vintage.

Cluster 2: Este cluster tem uma distribuição mais equilibrada entre Vintage Cars e Classic Cars, mas com uma presença menor de outros produtos, como Motorcycles, Trucks and Buses, e Planes. A quantidade média de pedidos é a mais baixa entre os clusters, e o preço médio por unidade também é o mais baixo. Isso sugere que os produtos neste cluster são itens de menor valor ou menos exclusivos.

Visualização dos cluster:

20) Utilizei um gráfico de dispersão, onde cada ponto representa um produto, e cores diferentes representam os diferentes clusters.

Validação:

21) Realizei uma validação cruzada de 5 vezes para o modelo KNN.
A validação cruzada de 5 vezes realizada para o modelo KNN resultou em acurácias que variam entre 0.8014 e 0.9504, com uma média de 0.8661 e um desvio padrão de 0.0567.

O modelo KNN apresenta uma acurácia média satisfatória, mas com alguma variabilidade entre as execuções da validação cruzada. Isso sugere que seu desempenho pode ser sensível às diferentes divisões dos dados, o que pode ser melhorado com ajustes nos hiperparâmetros e pré-processamento adequado.

Tomada de decisão:

           PRODUCTLINE  Cluster                         MarketingStrategy
0          Motorcycles        1  Focar em marketing específico e branding
1          Motorcycles        0          Reduzir preços e criar promoções
22         Motorcycles        2     Aumentar preços devido à alta demanda
26        Classic Cars        1  Focar em marketing específico e branding
124       Classic Cars        0          Reduzir preços e criar promoções
125       Classic Cars        2     Aumentar preços devido à alta demanda
212   Trucks and Buses        1  Focar em marketing específico e branding
237   Trucks and Buses        0          Reduzir preços e criar promoções
386   Trucks and Buses        2     Aumentar preços devido à alta demanda
475       Vintage Cars        1  Focar em marketing específico e branding
495       Vintage Cars        2     Aumentar preços devido à alta demanda
510       Vintage Cars        0          Reduzir preços e criar promoções
552             Planes        1  Focar em marketing específico e branding
573             Planes        2     Aumentar preços devido à alta demanda
782             Planes        0          Reduzir preços e criar promoções
935              Ships        0          Reduzir preços e criar promoções
936              Ships        1  Focar em marketing específico e branding
953              Ships        2     Aumentar preços devido à alta demanda
1065            Trains        1  Focar em marketing específico e branding
1072            Trains        0          Reduzir preços e criar promoções
2254            Trains        2     Aumentar preços devido à alta demanda
Teste t: estatística=1.8537, p-valor=0.0638

Relatório de Análise:
Média dos preços antes: 83.66
Média dos preços depois: 82.66
Teste t indica que não há diferença estatisticamente significativa nos preços.
