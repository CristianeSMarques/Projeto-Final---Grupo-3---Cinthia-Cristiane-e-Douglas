# Projeto-Final---Grupo-3---Cinthia-Cristiane-e-Douglas

# Análise de Acidentes de Trânsito — DATATRAN/PRF 2026

Projeto final da disciplina de Linguagens Técnicas de Programação (curso Analista de Dados II), 
usando Python, Pandas, NumPy e Git/GitHub para diagnosticar, tratar e analisar uma base pública real.

**Grupo 3**: Cristiane Marques · Cinthia Mabuchi · Douglas Almeida

## Sobre a base

Os dados vêm do **DATATRAN**, disponibilizado pelo Ministério da Infraestrutura / Polícia Rodoviária 
Federal (PRF), reunindo os registros de acidentes de trânsito em rodovias federais brasileiras.

- **Arquivo**: `datatran2026.csv`
- **Recorte temporal**: todos os acidentes registrados em janeiro a julho de 2026
- **Tamanho**: 42.322 registros, 30 colunas (um registro por acidente)

Principais colunas:
| Coluna | Significado |
|---|---|
| `data_inversa`, `horario`, `dia_semana` | Quando o acidente ocorreu |
| `uf`, `municipio`, `br`, `km` | Onde ocorreu |
| `causa_acidente`, `tipo_acidente`, `classificacao_acidente` | Como e por que ocorreu |
| `mortos`, `feridos_leves`, `feridos_graves`, `ilesos` | Consequências humanas |
| `condicao_metereologica`, `tipo_pista`, `tracado_via` | Condições da via/clima |

## Perguntas que guiaram a análise

1. Quais horários do dia concentram mais acidentes?
2. Quais dias da semana têm mais ocorrências?
3. Quais estados e municípios são mais críticos?
4. Quais tipos de acidente são mais frequentes?
5. Qual a gravidade dos acidentes (mortos/feridos) ao longo do período investigado?

## O que foi feito

- **Diagnóstico de qualidade**: verificação de faltantes, duplicados, categorias inconsistentes 
  e inconsistências lógicas entre colunas; comparação de métodos de outlier (IQR vs. z-score).
- **Limpeza e transformação**: tratamento de valores nulos, criação de colunas derivadas 
  (`faixa_gravidade`, `letalidade`, `total_vitimas`, entre outras de data/hora).
- **Análise exploratória**: cruzamentos com `groupby`, `merge` e `pivot_table`, com gráficos 
  interpretados em texto.
- **Conclusões**: achados voltados para leitura de negócio, com limitações e próximos passos.

## Como reproduzir

1. Clone o repositório: `git clone <url-do-repositorio>`
2. Instale as dependências: `pip install pandas numpy matplotlib seaborn jupyter`
3. Abra `Projeto.ipynb` no Jupyter ou VS Code e execute as células em ordem (`Run All`)

## Estrutura do repositório

├── Projeto.ipynb        # análise completa, do diagnóstico às conclusões
├── datatran2026.csv      # base de dados usada
├── README.md
└── .gitignore
