# 📊 Análise de Funil de Vendas — SQL, PostgreSQL & Dashboard Excel

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Excel](https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

## 🎯 Problema de Negócio

Uma empresa do setor automotivo precisa entender a eficiência do seu funil de vendas: quantos leads chegam, quantos convertem, qual o ticket médio e como essas métricas variam ao longo do tempo, por região e por marca. O objetivo foi extrair esses KPIs a partir de dados brutos no PostgreSQL e transformá-los em um dashboard executivo no Excel para apoiar decisões comerciais.

## 📊 Dashboard

![Dashboard Preview](Projeto%20Análise%20de%20Vendas.png)

[📄 Ver relatório completo em PDF](Projeto%20Análise%20de%20Vendas.pdf)

## 🛠️ Tecnologias Utilizadas

| Ferramenta | Uso |
|---|---|
| PostgreSQL | Banco de dados relacional |
| SQL (CTEs, Joins, EXTRACT) | Extração e transformação dos dados |
| pgAdmin 4 | Interface de desenvolvimento SQL |
| Microsoft Excel | Dashboard e visualização final |

## 🔍 Análises Realizadas

### KPIs Mensais
Cálculo de Receita Total, Volume de Leads, Taxa de Conversão e Ticket Médio utilizando `WITH (CTE)` e `DATE_TRUNC` para agrupamento temporal.

```sql
-- Exemplo de estrutura utilizada
WITH metricas_mensais AS (
  SELECT
    DATE_TRUNC('month', data_venda) AS mes,
    COUNT(DISTINCT lead_id)         AS leads,
    COUNT(DISTINCT venda_id)        AS vendas,
    SUM(valor)                      AS receita
  FROM vendas
  GROUP BY 1
)
SELECT
  mes,
  leads,
  vendas,
  ROUND(vendas::numeric / leads * 100, 2) AS taxa_conversao,
  ROUND(receita / NULLIF(vendas, 0), 2)   AS ticket_medio
FROM metricas_mensais
ORDER BY mes;
```

### Geolocalização de Vendas
Identificação dos estados com maior volume de conversões — São Paulo lidera com 2.463 unidades — para direcionamento de estratégias de marketing regional.

### Performance de Portfólio
Ranking de marcas e lojas mais vendidas utilizando `LEFT JOIN` entre tabelas de produtos e vendas, revelando os top 5 performers em cada categoria.

### Sazonalidade Semanal
Análise dos dias da semana com maior tráfego no site usando `EXTRACT('dow')`, identificando segundas e terças-feiras como picos de engajamento e finais de semana com queda acentuada.

## 📈 Principais Insights

| Insight | Resultado |
|---|---|
| Estado líder em vendas | São Paulo — 2.463 unidades |
| Dias de pico de tráfego | Segunda e terça-feira |
| Padrão de fim de semana | Queda significativa de visitas |
| Métrica central de negócio | Taxa de conversão por mês |

## 📂 Estrutura do Repositório

```
📁 Analise-Dados-PostgreSQL/
├── Análise de Funil de Vendas com SQL.sql   # Queries completas
├── Projeto Análise de Vendas.xlsx           # Dashboard Excel
└── Projeto Análise de Vendas.pdf            # Relatório exportado
```

## 🚀 Como Executar

1. Importe o dataset para uma tabela no PostgreSQL via pgAdmin
2. Execute as queries do arquivo `.sql` na ordem apresentada
3. Exporte os resultados para Excel
4. Abra o arquivo `.xlsx` para visualizar o dashboard final

## 📌 Aprendizados Técnicos

- Uso de CTEs (`WITH`) para organizar consultas complexas em etapas legíveis
- Aplicação de `DATE_TRUNC` e `EXTRACT` para análise temporal e sazonalidade
- `LEFT JOIN` para cruzamento de tabelas preservando registros sem correspondência
- Construção de dashboard executivo no Excel a partir de dados exportados do PostgreSQL

---

*Projeto desenvolvido como parte do MBA em Data Science e Analytics — USP/ESALQ*  
*Baseado no curso de SQL para Análise de Dados ministrado pela professora Midori Toyota*
