# 🗃️ Customer Segmentation Project

Este projeto foi desenvolvido com o desafio de aprimorar estratégias de negócios e marketing da empresa.

## Objetivos
- **Segmentação de Clientes:** Realizar a separação dos clientes em Clusters para entender seus comportamentos, preferências e aprimorar o direcionamento de estratégias para cada grupo.
- **Treinamento de Limpeza de Dados:** Implementar o algoritmo de Machine Learning K-Means após a preparação dos dados.

## Entrega Final
- Teremos o ID de cada cliente e seu cluster atribuído.
- Sugestões de estratégias de marketing adaptadas às características de cada Cluster.
- Recomendações para aprimorar a experiência do cliente com base nas particularidades de seus respectivos Clusters.

### Resultados
- Exemplo: Um determinado Cluster aceita mais campanhas de marketing, consome mais carnes e tem maior poder aquisitivo. Já outro Cluster apresenta alta possibilidade de Churn, exigindo atenção e estratégias específicas.

## Estrutura

    - Overview
    - Entendimento do Dataset
    - Exploração e Preparação dos Dados
        - Normalização das variáveis
    - Modelagem
        - Método de Elbow
        - Alocação de pesos
        - Aplicação do K-Means
    - Avaliação dos Resultados
        - Análise gráfica dos clusters
    - Resultados Finais

## Entendimento do Dataset:

- Importação de bibliotecas e dados necessários para o projeto.
- Os dados são públicos e foram obtidos no [Kaggle](https://www.kaggle.com/datasets/imakash3011/customer-personality-analysis).
- Configurações de ambiente e funções para evitar poluir o notebook.
- Primeiro contato com os dados para entender sua estrutura.

### 📊 Análises 
Entre as variáveis analisadas, temos o exemplo dos diferentes níveis de educação que os clientes possuem no cadastro:

![education](https://github.com/caiocasagrande/mkt_campaign_clustering/blob/main/images/education.png)

Além de usar as variáveis existentes no modelo (vinho, carne, doces, etc.), também construiu-se uma variável com o gasto geral dos clientes:

![quantidade_dinheiro_por_compra](https://github.com/caiocasagrande/mkt_campaign_clustering/blob/main/images/quantidade_dinheiro_por_compra.png)

## Normalização

- Visto que será empregado um algoritmo de distâncias (K-Means), é necessário que os dados estejam normalizados porque o algoritmo é sensível à escala das variáveis.
- Com a normalização, as variáveis passam para uma escala comum (de 0 a 1).
- Posteriormente, podemos atribuir pesos somente às variáveis em que faz "sentido de negócio" atribuir maior peso.

## Método de Elbow

- O método de Elbow é uma técnica utilizada em projetos de clusterização para determinar o número ideal de clusters em um conjunto de dados.
- A ideia é identificar o ponto no gráfico onde a adição de mais um cluster não resulta em uma melhoria significativa do modelo, auxiliando na escolha do número ideal.

![metodo_de_elbow](https://github.com/caiocasagrande/mkt_campaign_clustering/blob/main/images/metodo_elbow.png)

## Alocação de Pesos

- Realizada em conjunto com a equipe de negócios.
- Variáveis e seus pesos decididos conforme a importância atribuída a cada uma.
- Por exemplo, o total de dinheiro gasto é ponderado com peso 8 por sua alta importância na separação dos clientes.

# 🎯 Resultados

### Resumo das informações dos Clusters
- **Cluster 0: Maior Potencial**
  - 28,55% dos clientes.
  - Clientes de alta renda e alta educação com poucos filhos.
  - Alta renda, alta educação, maior gasto em vinhos e frutas.
  - Aceitação significativa de campanhas de marketing.

- **Cluster 1: Oportunidades de Crescimento**
  - 26,74% dos clientes.
  - Maior número de filhos por casa e maior gasto com doces.
  - Baixa renda, alta interação online, oportunidades para campanhas promocionais.

- **Cluster 2: Alta Rentabilidade**
  - 19,02% dos clientes.
  - Maior renda e maior educação entre os clusters.
  - Maior número de compras e maior dinheiro gasto.
  - Maior gasto em carnes, boa aceitação de campanhas.

- **Cluster 3: Buscar Engajamento**
  - 25,74% dos clientes.
  - Clientes mais jovens e de baixa renda.
  - Têm o menor gasto, alto número de compras com desconto.
  - Grupo que realiza o menor número de compras, é necessário maior atenção para evitar o Churn desses clientes.
 
### Análise gráfica dos clusters

![quantidade_de_compras_por_cluster](https://github.com/caiocasagrande/mkt_campaign_clustering/blob/main/images/quantidade_de_compras_por_cluster.png)

- É visível graficamente que o Cluster 2 possui o maior número de compras, seguido pelo Cluster 0.
- Os Clusters 1 e 3 apresentam semelhanças, mas ainda assim é possível ver que o menor número de compras está assossiado ao Cluster 3.
 
### **Sugestão de estratégias são orientadas conforme:**
  - **Marketing:** Campanhas personalizadas para cada Cluster.
  - **Produtos e Preços:** Ajustados de acordo com as preferências de cada grupo.
  - **Experiência do Cliente:** Aprimorada com foco nas particularidades de cada Cluster.

  > #### Exemplo de **estratégia** para o Cluster 2:
  > - **Marketing:** Destacar produtos premium, como carnes de alta qualidade, para atrair estes clientes dispostos a gastar mais;
  > - **Produtos e Preços:** Oferecer pacotes especiais e promoções em produtos de alto valor, aproveitando o maior poder aquisitivo desse grupo;
  > - **Experiência do Cliente:** Buscar **proporcionar atendimento especial** em razão do alto volume de compras. Implementar programas de fidelidade exclusivos em virtude das compras recorrentes e para construir relacionamentos duradouros.
