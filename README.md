# Otimização de Classificação com PCA, Seleção de Features e k-NN

## 1. O que é este projeto?

Este projeto é uma exploração prática na área de *Machine Learning* (Aprendizado de Máquina) focada em otimizar a forma como um modelo de Inteligência Artificial classifica informações. O seu principal objetivo é entender como a redução da complexidade dos dados afeta o desempenho e a precisão do algoritmo. 

Muitas vezes, bases de dados possuem dezenas ou centenas de características (variáveis), o que pode adicionar ruído, lentidão e confundir os modelos — um problema conhecido como "maldição da dimensionalidade". Para resolver isto, o projeto utiliza técnicas avançadas para simplificar os dados antes de os entregar à IA para aprendizagem:
* **PCA (Análise de Componentes Principais):** Uma técnica matemática que "comprime" as variáveis originais num número menor de componentes, tentando não perder a informação essencial.
* **Seleção de Features (Características):** O uso de um algoritmo (neste caso, o *Random Forest*) para identificar e selecionar apenas as variáveis que mais importam para prever o resultado.

O projeto aplica estas técnicas para treinar um modelo de classificação chamado **k-NN (k-Vizinhos Mais Próximos)**, avaliando se a simplificação dos dados ajuda o modelo a tomar decisões de forma mais eficiente e exata. Em suma, o projeto mostra na prática a pessoas e empresas que "menos é mais" na preparação de dados, permitindo criar sistemas preditivos mais leves, rápidos e, muitas vezes, mais precisos.

## 2. Como o fiz?

O projeto foi totalmente desenvolvido na linguagem Python, recorrendo a um ambiente interativo (Jupyter Notebook) e à biblioteca `scikit-learn`, uma das mais famosas na área de ciência de dados. O desenvolvimento seguiu um passo a passo estruturado:

1. **Obtenção e Geração dos Dados:**
   * Primeiramente, o sistema gerou artificialmente uma base de dados complexa, contendo 1000 exemplos e 20 variáveis.
   * Numa segunda fase, foi importada uma base de dados real e amplamente conhecida, o *Iris Dataset* (dados sobre características de flores).
2. **Preparação e Limpeza (Pré-processamento):**
   * **Divisão dos Dados:** A informação foi dividida em dois grupos: uma parte para treinar a IA e outra (separada e não vista pelo modelo) para testar se ele realmente aprendeu.
   * **Normalização:** Utilizou-se uma técnica para padronizar os valores (StandardScaler), garantindo que variáveis com escalas numéricas grandes não ofuscassem variáveis com valores mais pequenos.
3. **Redução de Dimensionalidade:**
   * Aplicou-se o algoritmo **PCA** nos dados artificiais de 20 variáveis para criar dois novos conjuntos mais simples: um com apenas 10 variáveis e outro com apenas 5 variáveis.
   * No caso dos dados das flores (*Iris*), utilizou-se o algoritmo **Random Forest** para calcular a pontuação de "importância" de cada característica das flores.
4. **Treino e Avaliação do Modelo (k-NN):**
   * Treinámos três versões do algoritmo k-NN: a primeira com todas as 20 variáveis originais, a segunda com 10 componentes e a terceira com 5 componentes.
   * Com o modelo treinado, pedimos para ele prever os dados de teste e comparámos os resultados através de métricas de acurácia (taxa de acerto).
5. **Resultados e Validação:**
   * Analisámos o desempenho final e concluímos que o modelo que utilizou apenas 5 componentes do PCA obteve a melhor performance (superando ligeiramente o modelo que usou todas as 20 variáveis originais).
   * Confirmou-se assim que a remoção de variáveis irrelevantes ou ruidosas otimiza a precisão da IA.

O processo de avaliação incluiu também métodos de validação cruzada para garantir que os resultados do modelo são robustos e que as conclusões obtidas são fiáveis.
