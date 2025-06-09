# 🧹 Análise de Tarefas Abandonadas (últimos 6 meses)

Este projeto tem como objetivo identificar tarefas que foram criadas e não concluídas em um período superior ao esperado, sinalizando possível **abandono**. Ele consulta dados armazenados no **Amazon DynamoDB**, analisa registros com **PySpark** e **Pandas**, e gera um relatório consolidado em `.CSV` e `.XLSX`.

## 🛠️ Tecnologias utilizadas

- Python 3.10+
- PySpark
- Pandas
- Boto3 (AWS SDK para Python)
- DynamoDB
- Dotenv
- Tabulate (exibição tabular no terminal)

## ⚙️ Critérios de abandono

- **Tarefa a Ser Feita**: considerada abandonada se estiver em aberto há mais de **15 dias**.
- **Item de Compra**: considerado abandonado se estiver em aberto há mais de **30 dias**.

## 📊 Saídas geradas

- Relatório de tarefas abandonadas por tipo e mês (últimos 6 meses)
- Arquivos:
  - `data/relatorioAbandono.csv`
  - `data/relatorioAbandono.xlsx`
- Tabela simulada no terminal

## 🧪 Execução e Observações
Este projeto foi desenvolvido para ser executado em ambiente Jupyter Notebook (.ipynb).

### ▶️ Como rodar?

Abra o arquivo `task/script.ipynb` no VSCode ou outro ambiente compatível.

Execute todas as células clicando em "Run All" (Executar tudo).

### ⚠️ Observação importante:

A execução do notebook realiza queries diretamente na tabela DynamoDB configurada no projeto (chave primária `LIST#<data>`). Isso significa que:

- Os dados refletirão em tempo real os conteúdos presentes na sua conta AWS.

- A análise e os relatórios dependerão dos dados armazenados no período de 6 meses anteriores à data atual.



