# Data Lake - Olimpiadas

Projeto de Data Lake local com dados dos Jogos Olimpicos, desde 1896 ate Paris 2024. Segue a arquitetura medallion com tres camadas: raw, bronze e gold.

## Como usar

1. O notebook `notebook.ipynb` na raiz gera as camadas raw e bronze
2. Cada subpasta em `olympics-datalake/gold/` tem seu proprio notebook com a analise especifica

### Dependencias

```
pip install pandas pyarrow matplotlib
```

## Estrutura do projeto

```
├── notebook.ipynb                  # Pipeline principal (raw + bronze)
├── dados-historicos/               # Dados fonte - olimpiadas historicas
├── dados-paris-2024/               # Dados fonte - Paris 2024
└── olympics-datalake/
    ├── README.md
    ├── metadata_schema.json
    ├── raw/                        # Dados brutos (CSV + metadados JSON)
    ├── bronze/                     # Parquet + datasets integrados
    └── gold/
        ├── analise_medalhas/       # Quadro de medalhas por pais
        ├── analise_modalidades/    # Ranking de esportes
        └── analise_genero/         # Evolucao por genero
```

## Fontes de dados

- World Olympedia (Kaggle) - Resultados olimpicos historicos (1896-2022)
- Paris 2024 Olympic Games (Kaggle) - Dados oficiais de Paris 2024
