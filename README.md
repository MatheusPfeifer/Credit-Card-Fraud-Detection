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

Para a entrega da solução, o modelo retornará a probabilidade da transação ser fraudulentas ou não.

## 3. Análise dos dados
O conjunto de dados que estamos utilizando foi pré-processado pela fonte de dados para evitar vazar qualquer tipo de informação dos seus clientes, as únicas variáveis que tem-se o nome são: Amount, que representa o valor da transação; e Class, que representa se a transação foi fraudulenta (1) ou não (0). 

A primeira coisa a se observar é que o conjunto de dados tem uma discrepância muito grande no número de observações para cada classe. Nos dados, encontramos 284315 casos de não-fraude, e apenas 492 casos de fraude. O que de certa forma é bom pois quer dizer a proporção de transações fraudulentas é baixa, porém para o treinamento do modelo isso é ruim, pois será mais difícil identificar padrões para as transações com fraude.

## 4. Modelo de Machine Learning
Para a construção do modelo, começei separando os dados de treino e validação, para poder avaliar a performance do modelo. E também utilizei duas abordagens para a escolha do algoritmo de Machine Learning. Primeiramente, utilizei a biblioteca PyCaret que funciona de forma mais automatizada e fornece 18 algoritmos de classificação, e dentre esses escolhi alguns para testar. Não utilizei todos os modelos, pois o conjunto de dados é relativamente grande, e demanda muito poder computacional para rodar os algoritmos. A segunda abordagem foi construir modelos de maneira mais manual, testei os modelos de Random Forest e Extreme Gradient Boosting, ambos modelos de classificação.

Além disso, testei duas abordagem para tratar o desbalanceamento de classes que citei acima, que foram o oversampling que consiste em usar técnicas estatísticas para aumentar sinteticamente os dados da classe minoritária (fraude), e o undersampling que consiste em diminuir os dados da classe maioritária. Detalhes mais técnicos são encontrados no código.

Após testar todos os modelos, o modelo que apresentou melhor performance, foi o Extreme Gradient Boosting que foi treinado utilizando os dados aplicando undersampling. O modelo teve uma acurácia de 97% para transações não-fraudulentas e 94% para transações fraudulentas, quando foi apresentado a novos dados, o que mostra uma boa performance do modeo. Abaixo, tem-se uma tabela com os resultados.

![image](https://user-images.githubusercontent.com/66805980/132138682-68f44833-5aee-4b16-8402-d9d4981d00fd.png)

## 5. Conclusão
Com os resultados do trabalho em mãos, pode ser visto o valor que uma solução utilizando Machine Learning pode trazer a um negócio. Com o modelo que foi obtido foi possível prever 94% das transações fraudulentas. Ou seja, traria economia para os clientes que sofreram com a fraúde, e economia para a empresa de cartão que provavelmente teria que devolver o dinheiro para o cliente. Todos nós estamos sujeitos a situações como essa, principalmente no caso de transações que utilizam cartão de forma online, então pode ser visto o valor que tem um projeto para prever fraude.

Como próximos passos para o projeto, poderia ser feita um solução em tempo real em que no momento que o cartão é utilizado, com o modelo em produção, é possível identificar se é uma fraude ou não, e se o modelo identificar como fraude, poderão ser tomadas as medidas pela empresa para interceptar a fraude.




