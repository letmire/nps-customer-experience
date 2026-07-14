<div align="center">
  <h1>📊 Global Express: NPS & Customer Experience (CX) Analytics</h1>
  <p><i>Projeto de Business Analytics focado em métricas de satisfação do cliente e otimização de canais de atendimento para e-commerce.</i></p>
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
Este projeto simula a atuação prática de um <b>Business Analyst</b> focado em analisar e otimizar a experiência de atendimento pós-compra em uma grande operação de e-commerce (Global Express). 
<br><br>
Neste repositório, foi estruturado um <b>Banco de Dados Relacional</b> contendo 800 feedbacks reais de clientes pós-interação. O objetivo principal foi avaliar o índice de satisfação geral via <b>NPS (Net Promoter Score)</b> e extrair consultas analíticas (SQL) para identificar gargalos operacionais e propor melhorias estratégicas à gestão de Customer Experience (CX).
</blockquote>

---

## 🛠️ Tecnologias e Funcionalidades

<table>
  <tr>
    <td><b>Tecnologia</b></td>
    <td><b>Aplicação no Projeto</b></td>
  </tr>
  <tr>
    <td>🐍 <b>Python (Pandas & Numpy)</b></td>
    <td>Engenharia de dados, geração da base simulada e classificação automatizada da jornada do cliente.</td>
  </tr>
  <tr>
    <td>🗄️ <b>SQLite</b></td>
    <td>Armazenamento seguro e estruturado dos dados no arquivo local <code>cx_analytics.db</code>.</td>
  </tr>
  <tr>
    <td>🔍 <b>SQL</b></td>
    <td>Consultas analíticas complexas aplicadas diretamente no banco de dados para extração rápida de KPIs.</td>
  </tr>
  <tr>
    <td>📊 <b>Excel</b></td>
    <td>Consumação da base tratada em CSV para visualização executiva e relatórios rápidos.</td>
  </tr>
</table>

---

## 🔍 Consultas SQL Aplicadas no Banco de Dados

### 1. Distribuição de Clientes (Cálculo de NPS)
Esta query analisa a volumetria e calcula a representatividade percentual de cada categoria de cliente (Promotores, Neutros e Detratores) na base de dados para entender a saúde da marca.

```sql
SELECT 
    Classificacao_NPS,
    COUNT(ID_Feedback) AS Quantidade,
    ROUND(COUNT(ID_Feedback) * 100.0 / (SELECT COUNT(*) FROM feedbacks), 2) AS Porcentagem
FROM 
    feedbacks
GROUP BY 
    Classificacao_NPS;
