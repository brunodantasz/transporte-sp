# Transporte Público na Região Metropolitana de São Paulo

Análise da distribuição das estações de metrô, corredores e terminais 
de ônibus na Região Metropolitana de São Paulo (RMSP).

## Fonte dos Dados

- **Centro de Estudos da Metrópole (CEM/USP)**
  - Estações de metrô em operação - RMSP 2025 (DOI: 10.55881/CEM.db.met006)
  - Corredores de ônibus - RMSP 2025 (DOI: 10.55881/CEM.db.cor002)
  - Terminais de ônibus - RMSP 2025 (DOI: 10.55881/CEM.db.tpa002)
  - Site: https://centrodametropole.fflch.usp.br/pt-br/download-de-dados

## Ferramentas Utilizadas

- **Python 3** — linguagem principal
- **geopandas** — leitura e manipulação de dados geográficos (shapefiles)
- **duckdb** — armazenamento dos dados em banco local
- **folium** — visualização de mapas interativos
- **matplotlib** — geração de gráficos
- **pandas** — manipulação de tabelas

## Estrutura do Projeto
projeto-transporte-sp/
├── coleta.ipynb              # Notebook de coleta e armazenamento dos dados
├── analise.ipynb             # Notebook de análise e visualização
├── dados/
│   ├── MEOP25_RMSP_CEM.shp  # Estações de metrô (+ arquivos auxiliares)
│   ├── ONCO25_RMSP_CEM.shp  # Corredores de ônibus (+ arquivos auxiliares)
│   ├── ONTE25_RMSP_CEM.shp  # Terminais de ônibus (+ arquivos auxiliares)
│   └── transporte_sp.duckdb  # Banco de dados DuckDB
└── README.md

## Como Executar

### 1. Coleta dos dados
- Acesse https://centrodametropole.fflch.usp.br/pt-br/download-de-dados
- Baixe os 3 arquivos zip:
  - Estações de metrô em operação - RMSP 2025
  - Corredores de ônibus - RMSP 2025
  - Terminais de ônibus - RMSP 2025
- Extraia os arquivos na pasta `dados/`
- Execute todas as células do `coleta.ipynb`

### 2. Análise dos dados
- Execute todas as células do `analise.ipynb`
- O mapa interativo será exibido diretamente no notebook

## Instalação das dependências

```bash
pip install geopandas duckdb folium matplotlib pandas
```

## Proposta de Análise

Com base nos dados coletados, propomos analisar a **equidade de cobertura 
por município** na RMSP:

- Cruzar as estações de metrô e terminais de ônibus com os limites municipais
- Calcular a densidade de equipamentos de transporte por km² em cada município
- Identificar municípios com menor acesso ao transporte de alta capacidade
- Comparar a cobertura com dados populacionais do IBGE Censo 2022

**Hipótese:** Municípios periféricos da RMSP possuem significativamente 
menos acesso ao transporte público de alta capacidade do que os municípios 
centrais, evidenciando desigualdade na distribuição da infraestrutura de 
mobilidade urbana.
