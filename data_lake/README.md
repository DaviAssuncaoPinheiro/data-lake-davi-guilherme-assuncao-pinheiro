# Data Lake - Olimpiadas

Data Lake local com dados olimpicos historicos (1896-2022) e Paris 2024, organizado em camadas seguindo a arquitetura medallion.

## Fontes de Dados

- **Dados Historicos**: World Olympedia - resultados de atletas em todas as edicoes dos Jogos Olimpicos (Kaggle)
- **Paris 2024**: Dados oficiais dos medalhistas das Olimpiadas de Paris 2024 (Kaggle)

## Estrutura

### raw/
Dados brutos originais em CSV com seus metadados em JSON.
- `olympics_historico.csv` - todos os resultados olimpicos historicos
- `olympics_paris2024.csv` - medalhistas de Paris 2024

### bronze/
Dados convertidos para Parquet e datasets integrados entre as fontes.
- `olympics_historico.parquet` - dados historicos em Parquet
- `olympics_paris2024.parquet` - dados Paris 2024 em Parquet
- `medalhas_1896_2024` - unificacao de todos os medalhistas (historico + Paris 2024)
- `modalidades_1896_2024` - contagem de medalhas por esporte e edicao
- `atletas_por_sexo` - medalhistas classificados por genero

### gold/
Analises finais com visualizacoes.
- `analise_medalhas/` - quadro de medalhas por pais (top 15)
- `analise_modalidades/` - ranking de esportes por medalhas
- `analise_genero/` - evolucao da participacao feminina ao longo do tempo

## Metadados

Cada dataset possui um arquivo JSON de metadados seguindo o schema definido em `metadata_schema.json`. Os metadados incluem: nome, fonte, descricao, colunas, quantidade de linhas, data de coleta e observacoes.
