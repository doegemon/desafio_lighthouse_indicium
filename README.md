# Desafio Programa Lighthouse - Indicium
O presente projeto de Ciência de Dados foi feito com base no desafio técnico proposto pela Indicium para participar do Programa Lighthouse.

O objetivo do projeto é identificar quais máquinas de uma determinada empresa apresentam potencial de falha, tendo como base dados extraídos através de sensores durante o processo de manufatura de produtos. 

Para tanto, foram fornecidos dois conjuntos de dados: um de Treino (com os atributos e a variável alvo) e um de Teste (somente com os atributos). 

# 01. Etapas do Projeto
Para conduzir o projeto, utilizei do método do CRISP, método cíclico de desenvolvimento composto das seguintes etapas: 
1. Entender o problema de negócio (no caso, acredito que seja prever que a máquina vai falhar antes de realmente falhar, de modo a realizar a manutenção preventiva); 
2. Entender o modelo de negócio da empresa (pulei essa etapa, já que não tinham muitos detalhes sobre a empresa); 
3. Coletar os dados (pegar os arquivos .csv disponibilizados); 
4. Limpeza dos dados - análise descritiva dos dados; 
5. Análise Exploratória de Dados - análise dos atributos e levantamento e validação de hipóteses; 
6. Preparação e modelagem dos dados - seleção de variáveis (*feature selection*)
7. *Machine Learning*; 
8. Avaliação dos modelos de *Machine Learning*; e
9. Previsão sobre os dados de Teste. 

# 02. Entregas
## 1. Descreva graficamente os dados disponíveis, apresentando as principais estatísticas descritivas. Comente o porquê da escolha dessas estatísticas.
**R**: A descrição gráfica dos dados, bem como as explicações estão expostas nas seções 2 e 3 (Descrição dos Dados e Análise Exploratória dos Dados) do Jupyter Notebook. 

## 2. Explique como você faria a previsão do tipo de falha a partir dos dados. Quais variáveis e/ou suas transformações você utilizou e por quê? Qual tipo de problema estamos resolvendo (regressão, classificação)? Qual modelo melhor se aproxima dos dados e quais seus prós e contras? Qual medida de performance do modelo foi escolhida e por quê?
**R**: Para prever o tipo de falha a partir dos dados, utilizei de algoritmos de Machine Learning, com o objetivo de encontrar padrões nos dados que possam indicar que uma máquina vai falhar. 
As variáveis e transformações utilizadas estão expostas nas seções 4 e 5 do Jupyter Notebook (Preparação dos Dados e *Feature Selection*)
Como estamos diante de uma variável alvo categórica, com mais de dois valores distintos e queremos prever o tipo de falha, estamos diante de um problema de Classificação com Multi-Classes. 
Após testar alguns algoritmos, adotei como algoritmo final o LGBMClassifier, por apresentar um *F1-Score* melhor que de seus pares. Esse algoritmo consiste em um framework de *gradient boosting* que usa algoritmos de aprendizado baseados em árvores.
Adotei essa métrica vez que, como não sei qual o objetivo da empresa com esse projeto (prever precisamente se uma falha vai acontecer ou conseguir prever todas as falhas possíveis nas máquinas), o *F1-Score* representa a média harmônica entre as métricas de *Precision* e *Recall*. 

## 3. Envie o resultado final do modelo em uma planilha com apenas duas colunas (rowNumber, predictedValues).
**R**: o arquivo .csv (*predicted.csv*) com as previsões do modelo se encontra dentro da pasta *data* do presente repositório.

## 4. Arquivos a serem entregues: 
- README: o presente arquivo, contendo as entregas e mais informações do projeto; 
- Requirements: *requirements.txt*, contendo as bibliotecas e pacotes do ambiente virtual utilizado; 
- Relatório de EDA: seções 2 e 3 do Jupyter Notebook *desafio_lighthouse_final.ipynb*;
- Código de Modelagem: seções 4, 5 e 6 Jupyter Notebook *desafio_lighthouse_final.ipynb*, bem como o modelo em formato .pkl se encontra dentro da pasta *model* do presente repositório; 
- Arquivo com as previsões: arquivo *predicted.csv* dentro da pasta *data* do presente repositório. 

# 03. Conclusões
Feita a Classificação do potencial de falha de uma máquina durante o processo de manufatura, a correta previsão de que uma máquina vai apresentar uma falha serve como gatilho para que seja feita uma manutenção preventiva, impedindo que a máquina falhe na produção do produto ou até mesmo quebre, acarretando em lentidão e prejuízos no processo produtivo. 

Por mais que a manutenção preventiva possa parar o processo de produção por um tempo, não se compara ao tempo que o processo produtivo ficaria parado caso uma máquina falhasse e viesse a quebrar. 

Espero que eu tenha atendido as exigências do desafio proposto pela Indicium, mas já valeu a pena pelo aprendizado de como lidar com problemas de Classificação com Multi-Classes e com classes desbalanceadas. 

# Referências
As referências usadas para o presente projeto se encontram na pasta *references* do repositório. 