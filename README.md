# credit-card-fraud-autoencoder
Detectando fraudes em cartões de crédito utilizando Redes Neurais Autoencoders (Aprendizado Não Supervisionado).
Detecção de Fraudes em Cartão de Crédito com Autoencoders (Deep Learning)

Este projeto utiliza uma arquitetura de rede neural do tipo Autoencoder para identificar transações fraudulentas em cartões de crédito. Diferente de modelos de classificação tradicionais, este projeto utiliza Aprendizado Não Supervisionado (Detecção de Anomalias), treinando a rede para aprender apenas o padrão das transações legítimas.

📌 Contexto do Problema
Fraudes bancárias possuem duas características desafiadoras:

Desbalanceamento Extremo: As fraudes representam menos de 0,2% do total de transações.

Evolução dos Padrões: Fraudadores mudam seu comportamento constantemente.

🧠 A Solução: Autoencoders
Um Autoencoder é uma rede neural projetada para aprender uma representação compacta dos dados de entrada e, em seguida, tentar reconstruir a entrada original.

A lógica aplicada:

O modelo foi treinado apenas com transações legítimas.

Ao encontrar uma transação normal, o erro de reconstrução (MSE) é baixo.

Ao encontrar uma fraude (anomalia), o modelo falha na reconstrução, gerando um MSE elevado. Esse erro serve como o "alarme" para identificar a fraude.

🛠️ Tecnologias Utilizadas
Linguagem: Python

Bibliotecas: TensorFlow/Keras, Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn.

Técnicas: StandardScaler, Redes Neurais MLP, Análise de Erro de Reconstrução.

📊 Resultados Obtidos
Após o treinamento de 50 épocas, o modelo apresentou os seguintes resultados com um Threshold (limite de decisão) de 1.8:

Erro Médio (Legítimas): 0.2606

Erro Médio (Fraudes): 3.4264

Taxa de Detecção (Recall): 50.7% das fraudes foram identificadas sem conhecimento prévio da classe.

Capacidade de Separação: O erro médio das fraudes foi aproximadamente 13x maior que o das transações normais, comprovando a eficácia do detector de anomalias.

🚀 Como Executar
Clone o repositório.

Certifique-se de ter o dataset creditcard.csv (Kaggle).

Execute o Jupyter Notebook ou script Python.

Ajuste o parâmetro threshold para equilibrar a Precisão vs Recall conforme a necessidade de negócio.
