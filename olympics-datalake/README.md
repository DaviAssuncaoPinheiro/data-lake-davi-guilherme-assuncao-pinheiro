# Data Lake - Olimpíadas

Data Lake local com dados olímpicos históricos (1896-2022) e Paris 2024, organizado em camadas seguindo a arquitetura medallion.

## Fontes de Dados

- **Dados Históricos**: World Olympedia - resultados de atletas em todas as edições dos Jogos Olímpicos (Kaggle)
- **Paris 2024**: Dados oficiais dos medalhistas das Olimpíadas de Paris 2024 (Kaggle)

## Estrutura

### raw/
Dados brutos originais em CSV com seus metadados em JSON.
- `olympics_historico.csv` - todos os resultados olímpicos históricos
- `olympics_paris2024.csv` - medalhistas de Paris 2024

### bronze/
Dados convertidos para Parquet e datasets integrados entre as fontes.
- `olympics_historico.parquet` - dados históricos em Parquet
- `olympics_paris2024.parquet` - dados Paris 2024 em Parquet
- `medalhas_1986_2024` - unificação de todos os medalhistas (histórico + Paris 2024)
- `modalidades_1986_2024` - contagem de medalhas por esporte e edição
- `atletas_por_sexo` - medalhistas classificados por gênero

### gold/
Análises finais com visualizações, cada uma com seu próprio notebook.
- `analise_medalhas/` - quadro de medalhas por país
- `analise_modalidades/` - ranking de esportes por medalhas
- `analise_genero/` - evolução da participação feminina ao longo do tempo

## Metadados

Cada dataset possui um arquivo JSON de metadados seguindo o schema definido em `metadata_schema.json`. Os metadados incluem: nome, fonte, descrição, colunas, quantidade de linhas, data de coleta e observações.
