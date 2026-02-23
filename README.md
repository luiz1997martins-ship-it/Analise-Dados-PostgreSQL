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

📈 Visualização de Dados

Os dados extraídos via SQL foram exportados para o Excel, onde realizei o tratamento final e a criação de um Dashboard contemplando:

Análise de Funil: Visualização da jornada desde o Lead até a Conversão.

Distribuição Geográfica: Identificação de que o estado de SP lidera as vendas com 2.463 unidades.

Sazonalidade: Identificação de picos de visitas no começo da semana e uma queda aos finais de semanas.

[Projeto Análise de Vendas.pdf](https://github.com/user-attachments/files/25501457/Projeto.Analise.de.Vendas.pdf)

<img width="1103" height="596" alt="image" src="https://github.com/user-attachments/assets/646d64ab-8e86-4837-8a33-942b009885cd" />





