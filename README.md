<!DOCTYPE html>
<html>
		
<body>

<h1>Machine Learning: Aluguel no Brasil</h1>
Este notebook foi desenvolvido para um case de negócio. O objetivo era prever o aluguel de moradias em algumas das maiores cidades do Brasil, utilizando como variáveis preditivas as características de cada imóvel como número de quartos, de banheiros, etc.<br><br>
O dataset utilizado pode ser encontrado neste <a href="https://www.kaggle.com/datasets/rubenssjr/brasilian-houses-to-rent">link</a>.<br>

<h2>Metodologia</h2>

<h3>Exploratory Data Analysis</h3>
Aqui foi feita a separação entre variáveis categóricas e numéricas, para que ambos os tipos de variáveis pudessem ser avaliados separadamente. A exploração foi feita através de histogramas na análise univariada e de gráficos de dispersão na análise bivariada. Além disso, foi feita uma análise para verificar a presença de dados duplicados ou ausentes.

<h3>Processamento de Dados</h3>
Durante o pré-processamento, algumas variáveis foram removidas por apresentar elevada correlação, visto que era basicamente uma soma para o total. Ademais, os dados foram divididos em treino e teste, usando a proporção de 70/30, respectivamente.<br><br>

<ul>
	<li><b>Padronização:</b> As variáveis numéricas foram padronizadas usando a função <code>StandardScaler</code>, para garantir que todas tivessem uma distribuição parecida (próxima de uma normal).</li>
	<li><b>Polinômios:</b> A fim de avaliar os modelos de outra maneira, os dados foram convertidos usando a função <code>PolynomialFeatures</code>, que gera uma combinação polinomial das variáveis.</li>
</ul>

<h3>Avaliação e Seleção do Modelo</h3>
Nesta parte, seis algoritmos diferentes – Linear Regression, Lasso e Ridge, Decision Tree Regressor, Random Forest Regressor e Epsilon-Support Vector Regression (SVR) – foram testados e avaliados em uma função criada com validação cruzada (<code>KFold</code>), usando métricas como R² Score, Root Mean Squared Error (RMSE) e Mean Absolute Error (MAE).<br>

Os modelos com os melhores resultados foram o Linear Regression com dados polinomiais e o Random Forest com dados padronizados. Como o modelo Random Forest possui hiperparâmetros disponíveis para tunagem, fez-se o teste usando a função <code>RandomizedSearchCV</code>.<br>

Na sequência, ambos os modelos foram avaliados com dados de teste e o Random Forest Regressor apresentou resultados levemente melhores.


<h2>Resultados</h2>
<p>Os resultados visuais do melhor modelo podem ser vistos abaixo.</p>

![image](https://github.com/gabrielfacheti/ml-aluguel-brasil/assets/106284497/4873f2dd-82ec-4975-8596-44b2a463655d)
![image](https://github.com/gabrielfacheti/ml-aluguel-brasil/assets/106284497/fd19da51-f6a9-4be9-ae05-2cdf7a126990)





</body>
</html>
