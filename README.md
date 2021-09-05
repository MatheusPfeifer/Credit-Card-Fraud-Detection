# Detecção de Fraudes em Cartão de Crédito

## 1. Contexto
O problema que será abordado, é o de fraude de cartão de crédito. Segundo dados da ClearSale, apenas no primeiro semestre de 2021 no Brasil, ocorreram mais de 2,6 milhões de tentativas de fraude utilizando o cartão de crédito. Ou seja, é um problema que afeta muitas pessosa que acabam com prejuízos financeiros, e também operadoras de cartão de crédito que muita das vezes precisam ressarcir o cliente.

Pensando nisso, uma solução para reduzir este problema é utilizar da ciência de dados, mais precisamente algoritmos de aprendizado de máquina, para poder identificar padrões em transações fraudulentas. Dessa forma, pode ser evitada que a fraude aconteça, trazendo economia de dinheiro e tempo, tanto os clientes quanto a empresa.

Os dados para construção do algoritmo se encontra no Kaggle, no link https://www.kaggle.com/mlg-ulb/creditcardfraud?select=creditcard.csv. E será usada a linguagem de programação Python junto com a IDE Jupyter notebook, para todo o processo de análise de dados.

## 2. Plano de Solução
Como foi dito anteriormente, iremos utilizar Machine Learning para identificar as transações que representam fraude baseado em dados históricos. O processo de análise foi divido em:
- Entendimento do problema de negócio
- Obtenção dos dados
- Análise exploratória dos dados
- Pré-processamento dos dados
- Criação do modelo
- Avaliação do modelo
- Entrega da solução

Para a entrega da solução, será fornecida uma tabela com a probabilidade das transações serem fraudulentas ou não.

## 3. Análise dos dados
O conjunto de dados que estamos utilizando foi pré-processado pela fonte de dados para evitar vazar qualquer tipo de informação dos seus clientes, as únicas variáveis que tem-se o nome são: Amount, que representa o valor da transação; e Class, que representa se a transação foi fraudulenta (1) ou não (0). 

A primeira coisa a se observar é que o conjunto de dados tem uma discrepância muito grande no número de observações para cada classe. Nos dados, encontramos 284315 casos de não-fraude, e apenas 492 casos de fraude. O que de certa forma é bom pois quer dizer a proporção de transações fraudulentas é baixa, porém para o treinamento do modelo isso é ruim, pois será mais difícil identificar padrões para as transações com fraude.

Em relação a variável amount, foi verificado que apresenta o mesmo comportamento para os casos de fraude e não-fraude.

## 4. Modelo de Machine Learning



