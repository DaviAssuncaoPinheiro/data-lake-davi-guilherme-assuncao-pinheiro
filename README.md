# Data Lake - Olimpiadas

Projeto de Data Lake local com dados dos Jogos Olimpicos, desde 1896 ate Paris 2024. Segue a arquitetura medallion com tres camadas: raw, bronze e gold.

## Como usar

O notebook `notebook.ipynb` executa todo o pipeline de dados. Basta rodar todas as celulas para gerar a estrutura completa do Data Lake.

### Dependencias

```
pip install pandas pyarrow matplotlib seaborn
```

## Estrutura do projeto

```
├── notebook.ipynb              # Notebook principal com todo o pipeline
├── dados-historicos/           # Dados fonte - olimpiadas historicas
├── dados-paris-2024/           # Dados fonte - Paris 2024
└── data_lake/
    ├── README.md               # Documentacao do Data Lake
    ├── metadata_schema.json    # Schema dos metadados
    ├── raw/                    # Dados brutos (CSV + metadados JSON)
    ├── bronze/                 # Dados em Parquet + datasets integrados
    └── gold/                   # Analises finais e visualizacoes
        ├── analise_medalhas/   # Quadro de medalhas por pais
        ├── analise_modalidades/# Ranking de esportes
        └── analise_genero/     # Evolucao da participacao por genero
```

## Fontes de dados

- [World Olympedia](https://www.kaggle.com/) - Resultados olimpicos historicos (1896-2022)
- [Paris 2024 Olympic Games](https://www.kaggle.com/) - Dados oficiais de Paris 2024
