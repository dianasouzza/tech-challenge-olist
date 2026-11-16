# Tech Challenge Olist: análise de e-commerce para investidores

Projeto da Fase 1 da Pós-Graduação em Data Analytics (FIAP). O objetivo é transformar dados transacionais da Olist em uma narrativa executiva sobre desempenho comercial, logística e satisfação do cliente, com recomendações para investidores.

## Status

Em andamento. Entrega final prevista para 17/01/2027.

- [x] Exploração inicial da base (Python)
- [ ] Escopo do projeto (trilhas e perguntas de negócio)
- [ ] Consultas SQL
- [ ] Modelo estrela e relatório no Power BI
- [ ] Apresentação executiva
- [ ] Vídeo executivo

## Pergunta norteadora

_A definir (será preenchida ao final do escopo)._

## Dados

Fonte: [Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (Kaggle). Cerca de 100 mil pedidos entre 2016 e 2018, em 9 tabelas. Confira a licença na página do dataset.

Os CSVs **não estão neste repositório**. Para reproduzir, baixe-os no Kaggle.

## Como reproduzir a exploração

1. Baixe os 9 CSVs no Kaggle.
2. Abra `notebooks/01_exploracao_base.ipynb` no Google Colab (botão "Open in Colab" no início do notebook).
3. Envie os CSVs para o painel de arquivos do Colab (ou ajuste a variável `PASTA` no início do notebook).
4. Execute todas as células.

## Estrutura do repositório

```
├── notebooks/   Notebooks de exploração e análise (Python)
├── sql/         Consultas SQL, uma por arquivo (em construção)
├── docs/        Escopo, dicionário de dados e regras de limpeza (em construção)
└── powerbi/     Relatório e imagens das páginas (em construção)
```

## Achados da exploração inicial

- Período: 04/09/2016 a 17/10/2018, com 99.441 pedidos (um por linha, sem duplicados).
- Cobertura: base sólida de jan/2017 a ago/2018 (20 meses). 2016 tem 329 pedidos e set/out de 2018 têm só 20.
- Status: 97,0% dos pedidos entregues.
- Entrega: 3,0% dos pedidos sem data de entrega ao cliente; 8 pedidos com status "delivered" sem data.
- Categorias: 73 em produtos e 71 na tabela de tradução (2 corrigidas); 1,4% dos itens sem categoria.
- Recompra: 3,1% dos clientes únicos compraram mais de uma vez (2.997 de 96.096).

## Decisões e regras de limpeza

- Cliente = `customer_unique_id` (o `customer_id` muda a cada pedido).
- Janela de análise sugerida: jan/2017 a ago/2018 (a confirmar).
- Análises de prazo usam apenas pedidos entregues com data de entrega.
- Itens sem categoria são mantidos e rotulados como "sem categoria".

## Ferramentas

Python (pandas, Plotly), SQL e Power BI.

## Autora

Diana Souza
