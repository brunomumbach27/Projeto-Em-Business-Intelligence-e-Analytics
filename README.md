#  Análise Preditiva da Produção Agrícola com BI e Dados Climáticos

##  Visão Geral
Este projeto analisa a produção agrícola no noroeste do Rio Grande do Sul, integrando **Business Intelligence (BI)** e **Analytics (Machine Learning)** para apoiar a tomada de decisão.

A solução combina:
-  Dashboards interativos (Power BI)
-  Modelos preditivos (Python)
-  Dados climáticos + agrícolas + geográficos

---

##  Objetivos
- Analisar o desempenho da produção agrícola por município e cultura  
- Identificar padrões e tendências ao longo do tempo  
- Avaliar o impacto de variáveis climáticas na produção  
- Construir modelos preditivos com base em dados históricos  
- Apoiar decisões estratégicas no setor agrícola  

---

##  Arquitetura da Solução
```text
 Coleta de Dados
   ├── IBGE (SIDRA) → Produção agrícola
   ├── INMET → Dados climáticos
   └── IBGE (BET) → Dados geográficos

 Processamento (Python)
   ├── Limpeza e padronização
   ├── Integração dos dados
   └── Feature engineering

 Armazenamento
   └── Arquivos CSV tratados

 BI (Power BI)
   ├── Modelagem dimensional
   ├── Medidas DAX
   └── Dashboards interativos

 Analytics (Machine Learning)
   ├── Treinamento
   ├── Avaliação
   └── Previsões
```

##  Estrutura do Projeto

```text
 projeto-em-business-intelligence-e-analytics/
│
├── data/
│   ├── dados_metereologicos/
│   │     ├──dados_extraidos/
│   │     └──dados_rs_tratados/
│   │         └──dados_meteorologia_RS.csv
│   ├── dados_producao_agricola/
│   │     └──dados_producao_noroeste_RS
│   └── daos_geograficos/
│        ├──RELATORIO_DTB_BRASIL_2024_MUNICIPIOS.xls
│        └──dados_tratados/
│            └──dados_geograficos_RS.csv
├── notebooks/
│    ├──data collection, cleaning, and processing/
│    │   ├── tratamento_dados_geograficos.ipynb
│    │   ├── tratamento_dados_meteorologicos.ipynb
│    │   └── tratamento_dados_producao.ipynb
│    └──predictive analytics
│        └──main.ipynb
├── dashboards/
│   └── dash.pbix
│
├── documents/
│   ├── Template - Fase 2 - Projeto em Business Intelligence e Analytics.pdf
│   └── Template - Fase 2 - Apresentação Executiva - Projeto em Business Intelligence e Analytics.pptx
│
└── README.md
```

## Dados Utilizados
### Produção Agrícola (IBGE - SIDRA)
    -Área plantada
    -Área colhida
    -Quantidade produzida
    -Valor da produção
    -Cultura (soja, milho, trigo, fumo)

### Dados Climáticos (INMET)
    -Precipitação (prec_total)
    -Temperatura média (temp_media)
    -Umidade média (umidade_media)
    -Vento médio (vento_media)

### Dados Geográficos (IBGE - BET)
    -Município
    -Região geográfica
    -Código IBGE

### Tratamento de Dados
  Padronização de colunas  
  Tratamento de valores nulos  
  Conversão de tipos  
  Integração entre bases

Desafio: Nem todos os municípios possuem estação meteorológica  
Solução: Agregação dos dados climáticos por região geográfica

## Business Intelligence (Power BI)
### KPIs
#### Produção Total

 Área Plantada / Colhida

 Valor da Produção

 Produtividade

 Distribuição geográfica
 
 Relação clima x produção

### Dashboards
Evolução da produtividade por ano

Área plantada por cultura

Valor da produção ao longo do tempo

Mapa de produção por município

Ranking de produtores

Análise por cultura


## Análise Preditiva
### Modelo
```python
from sklearn.ensemble import RandomForestRegressor

model = RandomForestRegressor(n_estimators=200, random_state=42)
model.fit(X_train, y_train)
```

### Métricas
R²: ~0.68

MAE: ~368

### Importância das Variáveis
 Temperatura média → maior impacto

 Umidade → impacto relevante

 Precipitação → menor influência

### Previsão
```python
novo_dado = pd.DataFrame({
    'prec_total': [150],
    'temp_media': [24],
    'umidade_media': [75]
})
```

 ### Principais Insights
 Forte dependência da soja

 Produção concentrada em poucos municípios

 Crescimento da área plantada ao longo do tempo

 Clima influencia diretamente a produtividade

 Baixa diversificação agrícola

## Conclusão
A integração entre BI e Analytics permitiu:

Melhor visualização dos dados

Identificação de padrões

Geração de previsões

Apoio à tomada de decisão

 ## Tecnologias

Python
Pandas / NumPy  
Scikit-learn  
Matplotlib / Seaborn  
Power BI  
GitHub  

Documentação  
  Relatório técnico (PDF)  
  Apresentação executiva (PPT)  
  Dashboard (Power BI)  
  Código fonte (GitHub)  

## Autor
Bruno Enrique Mumbach PUCRS