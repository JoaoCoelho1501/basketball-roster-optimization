# Otimização de Plantel com Programação Linear Inteira: Boston Celtics

> Modelo em Gurobi que escolhe o cinco inicial com melhor performance agregada, respeitando o orçamento de bónus e restrições táticas.

**Mestrado em Business Intelligence & Analytics (ISCAP)**, 2025/26

## O problema
Escolher **5 de 18 jogadores** dos Boston Celtics (NBA) de forma a **maximizar o overall agregado**, ponderado por pesos posicionais, cumprindo estas restrições:
- orçamento de bónus por jogo de no máximo **1 milhão de dólares**;
- no máximo **2 jogadores por posição**;
- pelo menos **1 Power Forward**;
- exclusão de jogadores com *Score* < 0,25.

## Abordagem
1. Cálculo de um *Player_Overall* normalizado (MinMaxScaler) a partir das estatísticas.
2. Formulação em **Programação Linear Inteira**, com variáveis binárias de seleção.
3. Resolução com **Gurobi** (`gurobipy`) no Google Colab.

## Resultado
O modelo não escolhe simplesmente os 5 melhores jogadores. Escolhe a combinação que maximiza o desempenho coletivo dentro do orçamento, ou seja, resolve o equilíbrio entre qualidade e custo, que se aplica a qualquer problema de alocação de recursos limitados.

## Stack
`Python` · `Gurobi (gurobipy)` · `pandas` · `scikit-learn`

## Como correr
Abre o notebook no Google Colab e carrega o ficheiro `Celtic_Stats.csv` (separador `;`) quando for pedido.

## Autores
Beatriz Teixeira · João Coelho · João Vasques · Rui Parada
