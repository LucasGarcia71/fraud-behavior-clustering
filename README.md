# fraud-behavior-clustering

Exploração de padrões comportamentais em transações financeiras via clusterização não supervisionada, sem dependência de target ruidoso.

## Sobre

Estudo aplicado de detecção de fraude sem dependência de target confiável.

A abordagem parte de feature engineering comportamental por portador do cartão
(volume, desvio histórico, concentração de produto, diversidade de dispositivos)
e usa K-Means em múltiplos K para identificar quais variáveis naturalmente
separam grupos de comportamento.

O ranking de features por estabilidade de centroides alimenta um LightGBM,
testado em duas configurações: com e sem o cluster label como feature adicional.

## Dataset

IEEE-CIS Fraud Detection — Kaggle (590k transações, 394 features)

## Estrutura

fraud-behavior-clustering/
├── codigo/
│ └── feature_engineer.ipynb
├── dados/ # CSVs não versionados — baixar via Kaggle
├── output/
└── README.md


## Resultado

| Abordagem | AUC-PR |
|---|---|
| Features comportamentais (sem cluster) | 0.1400 |
| Features comportamentais + cluster label | 0.1423 |
