# Analise-Dados-PostgreSQL

Análise de Funil de Vendas e Performance com SQL (PostgreSQL)

📋 Sobre o Projeto
Este projeto consiste na extração e análise de dados de um funil de vendas fictício para identificar padrões de comportamento de clientes, performance de vendas por região e marcas, e eficiência de conversão. O objetivo foi transformar dados brutos armazenados em um banco PostgreSQL em indicadores de negócio (KPIs) prontos para visualização.

🛠️ Tecnologias Utilizadas

Banco de Dados: PostgreSQL
Interface: pgAdmin 4
Linguagem: SQL
Visualização: Excel (Gráficos e Dashboards) 

🔍 Principais Análises Realizadas (Queries)

KPIs Mensais: Cálculo de Receita, Leads, Taxa de Conversão e Ticket Médio utilizando WITH (CTE) e DATE_TRUNC.

Geolocalização: Identificação dos estados com maior volume de vendas para direcionamento de marketing.

Performance de Portfólio: Ranking de marcas e lojas mais vendidas através de LEFT JOIN entre as tabelas de produtos e vendas.

Sazonalidade Semanal: Análise dos dias da semana com maior tráfego no site utilizando a função EXTRACT('dow').
