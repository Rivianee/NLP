Projeto de Classificação de Categorias com NLP

Este é um projeto  inclui várias etapas, desde a análise exploratória até a criação de uma API para fornecer previsões em tempo real.

## Objetivo

O objetivo deste projeto é explorar um conjunto de dados, criar modelos de CLASSIFICAÇÃO com machine learning e disponibilizar uma API para interação com o modelo.
Este projeto visa classificar notícias em diferentes categorias usando técnicas de Processamento de Linguagem Natural (PLN) e aprendizado de máquina. O modelo principal utilizado é a Regressão Logística, que foi treinado e avaliado em um conjunto de dados de notícias pré-processadas.

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

- `analise_exploratoria.ipynb`: Notebook contendo a análise exploratória dos dados e o pré- processamento dos dados.
- `treinamento_modelo.ipynb`: Notebook com o treinamento dos modelos de machine learning e o script Python contendo a implementação da API Flask.
- `requirements.txt`: Arquivo de requisitos Python para instalação das dependências.

## Configuração

Para executar este projeto localmente, siga estas etapas:

1. Clone este repositório: `git clone https://github.com/seu-usuario/projeto.git`
2. Instale as dependências: `pip install -r requirements.txt`
3. Execute a aplicação: `python app.py`
4. Acesse a API em http://localhost:5000 para fazer as classificações

## Entendimento do projeto e testes realizados

O projeto apresenta várias categorias para classificação:

category
poder        11011
mercado      10485
esporte       9865
mundo         8565
cotidiano     8484
educacao      1059
turismo        952
ciencia        667
comida         414

Sendo possível observar um desbalanceamento das categorias, contudo em testes de modelagem optamos por não inserir dados, apenas testar na modelagem se a definição class_weight faria uma diferença na resposta do modelo e não teve um aumento de resposta de acurácia, sendo inclusive observado uma redução de 1% na acurácia.

## Pré processamento

Para o cada etapa do pré-processamento, foi realizado:

Lowercasing e remoção de pontuação: Todas as letras do texto foram convertidas para minúsculas para garantir consistência e facilitar a comparação. Em seguida, a pontuação foi removida para simplificar o texto e focar apenas nas palavras.

Tokenização: O texto foi dividido em tokens (palavras individuais) para análise subsequente.

Remoção de stopwords: Foram removidas as palavras comuns que não contribuem muito para o significado do texto, como artigos, preposições e conjunções. Isso ajuda a reduzir o ruído nos dados.

Lemmatization: As palavras foram lematizadas para reduzi-las à sua forma base (lemas), o que ajuda na normalização do texto e na redução da dimensionalidade do vocabulário. Isso também ajuda a tratar palavras com variações morfológicas.

Normalização de acentos: Os acentos foram normalizados para garantir consistência e uniformidade no texto.

Combinação de tokens pré-processados: Os tokens pré-processados foram combinados novamente em uma única string para representar o texto final, pronto para análise e modelagem.

Além das etapas padrão, foi essencial analisar a frequência das palavras por categoria e realizar a remoção de palavras que não foram consideradas essenciais, aumento a acurácia da modelagem de 0.92 para 0.94.

##Treinamento e Avaliação do Modelo

Utilizamos a Regressão Logística com TF-IDF Vectorizer. O modelo é ajustado utilizando GridSearchCV para encontrar os melhores hiperparâmetros. O pipeline completo inclui etapas de transformação e modelagem.

## Resultados
O modelo treinado foi avaliado no conjunto de teste, gerando um relatório de classificação que inclui precisão, revocação, F1-score e acurácia. O desempenho geral do modelo foi satisfatório, com uma acurácia de aproximadamente 92%.

## Contribuições
Contribuições são bem-vindas! Se você deseja contribuir com este projeto, por favor, abra uma issue ou envie um pull request.
