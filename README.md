# 📌 Consultas SQL - Faturamento e Receita Mensal

## 📖 Descrição
Este projeto contém consultas SQL para analisar o faturamento por estado e a receita mensal por área do conhecimento de uma instituição de ensino. As consultas utilizam junções entre tabelas para obter informações agregadas e ordenadas.

## 📌 Funcionalidades
- Calcular o faturamento total por estado.
- Determinar a receita mensal da instituição por área do conhecimento.
- Utiliza consultas com `JOIN`, `SUM()` e `GROUP BY` para agrupar e sumarizar os dados.

## 🚀 Consultas SQL
### 1️⃣ Faturamento por Estado
```sql
SELECT C.UF AS ESTADO, SUM(M.VALOR) AS FATURAMENTO
FROM MATRICULA M
INNER JOIN ALUNOS AL ON AL.CPF = M.ALUNO
INNER JOIN CIDADES C ON C.CODIGO = AL.CIDADE
GROUP BY C.UF
ORDER BY FATURAMENTO DESC;
```
📌 **Explicação:**
- Agrupa os dados por estado (`UF`).
- Calcula o faturamento somando os valores (`SUM(M.VALOR)`).
- Ordena em ordem decrescente de faturamento.

### 2️⃣ Receita Mensal por Área do Conhecimento
```sql
SELECT CS.NOME AS ÁREA_DO_CONHECIMENTO, SUM(M.VALOR) AS RECEITA_MENSAL
FROM MATRICULA M
INNER JOIN CURSOS CS ON CS.CODIGO = M.CURSO
GROUP BY CS.NOME
ORDER BY RECEITA_MENSAL DESC;
```
📌 **Explicação:**
- Agrupa os dados por área do conhecimento.
- Calcula a receita mensal somando os valores (`SUM(M.VALOR)`).
- Ordena os resultados da maior para a menor receita.

## 🛠 Tecnologias Utilizadas
- **Banco de Dados Relacional (SQL)**
- **MySQL** (ou compatível, como PostgreSQL, SQL Server)

## 📝 Como Utilizar
1. Certifique-se de ter um banco de dados compatível.
2. Copie e cole as consultas em seu gerenciador SQL.
3. Execute as consultas e visualize os resultados.

---
**© 2025 - Desenvolvido por Nicollas Meneses**

