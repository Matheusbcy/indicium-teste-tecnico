# 🎬 Projeto de Análise e Predição IMDB

Este projeto realiza análise exploratória de dados (EDA) e predição da nota IMDB de filmes a partir de variáveis como ano de lançamento, gênero, diretor, elenco, entre outras.  
Foram treinados e avaliados 3 modelos de Machine Learning (**Gradient Boosting**, **DecisionTreeRegressor**, **RandomForestRegressor**) para prever a nota de novos filmes.

---

## 📁 Dataset

- **Arquivo**: `desafio_indicium_imdb.csv`  
- **Principais colunas**:  
  - Series_Title  
  - Released_Year  
  - Certificate  
  - Runtime  
  - Genre  
  - IMDB_Rating  
  - Overview  
  - Meta_score  
  - Director  
  - Star1, Star2, Star3, Star4  
  - No_of_Votes  
  - Gross  

---

## 📦 Requisitos (versões usadas)

- Python 3.10 ou superior  
- pandas 2.3.1  
- numpy 2.2.6  
- seaborn 0.13.2  
- matplotlib 3.10.3  
- scikit-learn 1.6.1  
- joblib 1.4.2  

As dependências acima constam no arquivo `requirements.txt` do projeto.

---

## ⚙️ Instalação

1. Instale o **Python 3.10** ou superior no seu sistema.  
2. Crie e ative um **ambiente virtual** de sua preferência.  
3. Instale as dependências listadas no `requirements.txt`.  
4. Caso queira replicar exatamente o ambiente utilizado, utilize as versões indicadas na seção de requisitos.  

---

## ▶️ Como executar

1. Coloque o arquivo `desafio_indicium_imdb.csv` na raiz do projeto.  
2. Execute o script principal (`LH_CD_MATHEUS_FREITAS.ipynb`) para:  
   - carregar e limpar os dados,  
   - realizar a EDA,  
   - treinar e avaliar os modelos,  
   - salvar o melhor modelo treinado no arquivo `model_boosting.pkl`.  
3. Para realizar previsões, carregue o arquivo `model_boosting.pkl` no seu script de inferência e aplique o mesmo pré-processamento utilizado no treinamento.  

---

## 🔎 EDA (principais achados)

- Total de títulos após limpeza: **713 itens**.  
- Período coberto: **1930 a 2019**.  
- Certificados mais comuns: **U, A, UA e R**.  
- Gêneros mais frequentes:  
  - Drama  
  - Drama e Romance  
  - Comedy e Drama  
  - Crime, Drama e Thriller  
  - Action, Adventure e Sci-Fi  
- Duração média dos filmes: **123,7 minutos**.  
- Atores mais recorrentes: Robert De Niro, Al Pacino, Tom Hanks, Brad Pitt, Christian Bale.  
- Diretores mais recorrentes: Steven Spielberg, Martin Scorsese, Alfred Hitchcock, David Fincher, Clint Eastwood.  

---

## 🧪 Modelagem

- **Alvo da regressão**: `IMDB_Rating`  
- **Variáveis preditoras**: todas as demais colunas, exceto `Series_Title` e `Overview`.  

### Tratamentos realizados:
- remoção de nulos,  
- conversão de tipos (ex.: `Runtime` para numérico),  
- limpeza de `Gross` para numérico,  
- codificação de variáveis categóricas com **One-Hot Encoding**.  

### Modelos testados:
- Decision Tree Regressor  
- Random Forest Regressor  
- Gradient Boosting Regressor  

### Validação:
- Validação cruzada com **K-Fold**  

---

## 📈 Resultados (resumo)

- **Desempenho médio em validação cruzada**:  
  - Decision Tree → ~0,3909  
  - Random Forest → ~0,5724  
  - Gradient Boosting → ~0,5786  

- **Métrica no conjunto de teste do melhor modelo (Gradient Boosting):**  
  - Erro quadrático médio (**MSE**) ≈ 0,0419  

➡️ O modelo **Gradient Boosting** apresentou o melhor equilíbrio entre desempenho e estabilidade.  

---

## 💾 Modelo salvo

- **Arquivo**: `model_boosting.pkl`  
- **Conteúdo**: modelo Gradient Boosting treinado com os melhores hiperparâmetros.  

⚠️ Observação: para usar o modelo, é obrigatório aplicar o **mesmo pré-processamento** dos dados (incluindo One-Hot Encoding e transformações numéricas) antes da inferência.  

---

## 🧠 Observações sobre NLP (Overview)

- Foi testada uma classificação de gênero baseada apenas no texto da sinopse (`Overview`) com **TfidfVectorizer + Logistic Regression**.  
- O desempenho foi limitado para classes pouco frequentes (Family, Mystery, Western).  

---

## ✅ Checklist de reprodução

- [x] Ter Python 3.10 ou superior instalado.  
- [x] Criar e ativar um ambiente virtual.  
- [x] Instalar as dependências do `requirements.txt`.  
- [x] Garantir o arquivo `desafio_indicium_imdb.csv` na raiz.  
- [x] Executar o script principal para gerar análises, treinar e salvar o modelo.  

---

## 👤 Autor

Projeto desenvolvido por **Matheus**, para teste técnico de Ciência de Dados da Indicium  
