<div align="center">
  <h1>📊 Global Express: NPS & Customer Experience (CX) Analytics</h1>
  <p><i>Projeto de Analista de Performance e Dados focado em métricas de satisfação do cliente e otimização de canais de atendimento para e-commerce.</i></p>
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white" alt="SQLite">
  <img src="https://img.shields.io/badge/SQL-CC2927?style=for-the-badge&logo=databricks&logoColor=white" alt="SQL">
  <img src="https://img.shields.io/badge/Microsoft_Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white" alt="Excel">
</p>

---

## 📌 Sobre o Projeto

<blockquote>
Este projeto simula a atuação prática de um <b>Analista de Performance e Dados</b> focado em analisar e otimizar a experiência de atendimento pós-compra em uma operação de e-commerce. 
<br><br>
Neste repositório, preparei e modelei um dataset de 800 feedbacks de clientes dentro de um banco de dados relacional. O objetivo foi avaliar o índice de satisfação via <b>NPS (Net Promoter Score)</b> e extrair dados para identificar gargalos operacionais e propor melhorias para a gestão de Customer Experience (CX).
</blockquote>

---

## 🛠️ Tecnologias e Funcionalidades

<table>
  <tr>
    <td><b>Tecnologia</b></td>
    <td><b>Aplicação no Projeto</b></td>
  </tr>
  <tr>
    <td>🐍 <b>Python (Pandas)</b></td>
    <td>Manipulação, limpeza de dados e classificação da jornada do cliente.</td>
  </tr>
  <tr>
    <td>🗄️ <b>SQLite</b></td>
    <td>Estruturação e armazenamento dos dados em um banco relacional.</td>
  </tr>
  <tr>
    <td>🔍 <b>SQL</b></td>
    <td>Extração de indicadores de desempenho (KPIs) para identificar padrões de comportamento.</td>
  </tr>
  <tr>
    <td>📊 <b>Excel</b></td>
    <td>Análise e visualização dos dados exportados para relatórios.</td>
  </tr>
</table>

---

## 🔍 Consultas SQL Aplicadas

### 1. Distribuição de Clientes (Cálculo de NPS)
Esta query analisa a volumetria e calcula a representatividade percentual de cada categoria de cliente (Promotores, Neutros e Detratores) para entender a saúde da marca.

```sql
SELECT 
    Classificacao_NPS,
    COUNT(ID_Feedback) AS Quantidade,
    ROUND(COUNT(ID_Feedback) * 100.0 / (SELECT COUNT(*) FROM feedbacks), 2) AS Porcentagem
FROM 
    feedbacks
GROUP BY 
    Classificacao_NPS;
