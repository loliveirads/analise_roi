# 📊 Análise de ROI em Campanhas Publicitárias

Este projeto tem como objetivo construir um modelo de regressão linear capaz de prever o aumento esperado nas vendas com base no investimento em publicidade e no tipo de mídia utilizada. A análise busca auxiliar na **tomada de decisão estratégica**, identificando quais canais oferecem melhor retorno sobre o investimento (ROI).

---

## 📁 Estrutura do Projeto

- `Gastos_Publicidade_MelhoresCompras.csv` → Base de dados com campanhas publicitárias.
- `notebook_analise.ipynb` → Notebook com toda a análise exploratória, modelagem e interpretação.
- `modelo_regressao.pkl` → Modelo treinado com `LinearRegression`.
- `encoder_midia.pkl` → Transformador (OneHotEncoder) utilizado para lidar com variáveis categóricas.
- `simulador.py` → Script para prever vendas simuladas com diferentes mídias e orçamentos.

---

## ⚙️ Técnicas Utilizadas

- 📦 **Scikit-learn** para modelagem e pré-processamento
- 📈 **Regressão Linear** para estimar a relação entre investimento e retorno
- 🧠 **OneHotEncoder** via `ColumnTransformer` para variáveis categóricas
- 💾 **Pickle** para salvar modelo e encoder
- 📊 Visualizações com **Seaborn** e **Matplotlib**

---

## 🔍 Coeficientes do Modelo

## 🔢 Variáveis Contínuas

| Variável                           | Coeficiente | Interpretação |
|-----------------------------------|-------------|----------------|
| **Ano**                           | +52,15      | A cada novo ano, espera-se um aumento médio de **52 mil unidades** na previsão de vendas. |
| **Mês**                           | +30,55      | Indica um possível efeito sazonal ou tendência positiva de **~30 mil unidades**. |
| **Gastos com Publicidade (em R$)**| +0,0102     | Para cada **R$ 1 investido**, o aumento previsto é de ~0,0102 mil unidades (**10,2 unidades**).  

Para **R$ 1.000** investidos, espera-se um retorno de **~10.200 unidades**.  
Para **R$ 100.000**, espera-se **~1.020.000 unidades vendidas**. |

Cada coeficiente representa o **impacto médio** de uma variável na previsão de vendas, mantendo as outras constantes.

| Tipo de Mídia     | Coeficiente | Interpretação                                  |
|-------------------|-------------|-----------------------------------------------|
| **Instagram**     | –25         | ROI **muito próximo ao Google**. Diferença pequena e estatisticamente pouco relevante. |
| **Páginas Web**   | –2.649      | Queda moderada no retorno esperado. |
| **Revista**       | –3.090      | Redução acentuada no desempenho. |
| **Rádio**         | –3.184      | Impacto negativo mais expressivo. |
| **Jornal**        | –3.336      | ROI consideravelmente inferior à Google. |
| **Redes Sociais** | –3.361      | Desempenho um pouco abaixo da média. |
| **TV**            | –3.898      | 📉 **Pior desempenho previsto** entre todas as mídias. |


---

## 🧪 Simulação

Com o modelo salvo, é possível prever quantas unidades podem ser vendidas em diferentes cenários:

```bash
prever_vendas(tipo_midia="Google", ano=2024, mes=8, gasto=100000)
prever_vendas(tipo_midia="TV", ano=2024, mes=8, gasto=100000)
```

## 🚀 Como Executar Localmente (usando Poetry)

1. Clone o repositório:

```bash
git clone git@github.com:loliveirads/analise_roi.git
cd analise_roi
```

2. Instale o Poetry (se ainda não tiver):

```bash
pip install poetry
```

3. Ative o ambiente virtual:

```bash
poetry shell
```

4. Instale as dependências do projeto:

```bash
poetry install
```
5. Crie o kernel Jupyter (caso deseje executar notebooks):

```bash
python -m ipykernel install --user --name=analise-roi --display-name "Python (Análise ROI)"
```

5. Execute os scripts ou abra o Jupyter Notebook:

```bash
jupyter notebook
```

## 👤 Autor

**Luiz Fernando**  
📧 [luizfsoliveira.lm@gmail.com](mailto:luizfsoliveira.lm@gmail.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/loliveirads)  
🐙 [GitHub](https://github.com/loliveirads)
