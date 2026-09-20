# Projeto-Final---Grupo-3---Cinthia-Cristiane-e-Douglas

# Análise de Acidentes de Trânsito — DATATRAN/PRF 2026

Projeto final da disciplina de Linguagens Técnicas de Programação (curso Analista de Dados II), 
usando Python, Pandas, NumPy e Git/GitHub para diagnosticar, tratar e analisar uma base pública real.

**Grupo 3**
* Cristiane Marques 
* Cinthia P M Tirulli 
* Douglas Almeida

## Sobre a base

Os dados foram extraídos do portal do **DATATRAN**, mantido pela Polícia Rodoviária Federal (PRF). O conjunto reúne informações sobre acidentes de trânsito registrados em rodovias federais brasileiras.

- **Arquivo**: `datatran2026.csv`
- **Recorte temporal**: todos os acidentes registrados em janeiro a julho de 2026
- **Tamanho**: 42.322 registros, 30 colunas (um registro por acidente)

Principais variáveis trabalhadas:
- **Temporais:** `data_inversa`, `horario`, `dia_semana`, além de variáveis derivadas (`ano`, `mes`, `dia`, `hora`, `nome_mes`, `nome_dia`). Indicam quando o acidente ocorreu.
- **Espaciais:** `uf`, `municipio`, `br`, `km`, `regional`, `delegacia`, `uop`. Indicam onde ocorreu.
- **Circunstanciais:** `causa_acidente`, `tipo_acidente`, `classificacao_acidente`, `fase_dia`, `sentido_via`. Indicam como e por que ocorreu.
- **Vítimas e severidade:** `mortos`, `feridos_leves`, `feridos_graves`, `ilesos`,  `pessoas`. Indicam consequências humanas.
- **Condições de Via e Clima (Fatores Externos):**  `condicao_metereologica`, `tipo_pista`, `tracado_via`. Indicam condições da via/clima.

## Perguntas que guiaram a análise

1. Quais horários do dia concentram mais acidentes?
2. Quais dias da semana têm mais ocorrências?
3. Quais estados e municípios são mais críticos?
4. Quais tipos de acidente são mais frequentes?
5. Qual a gravidade dos acidentes (mortos/feridos) ao longo do período investigado?

## O que foi feito

- **Diagnóstico de qualidade**: verificação de faltantes, duplicados, categorias inconsistentes e inconsistências lógicas entre colunas; comparação de métodos de outlier (IQR vs. z-score).
- **Limpeza e transformação**: tratamento de valores nulos, padronização de municípios (`.str.title()`) e saneamento de categorias, criação de colunas derivadas   (`faixa_gravidade`, `letalidade`, `total_vitimas`, entre outras de data/hora).
- **Análise exploratória**: cruzamentos com `groupby`, `merge` e `pivot_table`, estudo de sazonalidade temporal com média móvel via vetores NumPy (`np.convolve`), com gráficos interpretados em texto.
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
