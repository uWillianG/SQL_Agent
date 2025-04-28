# SQL_Agent
Agente de IA que faz análises do histórico de IPCA, permitindo raspar dados oficiais, armazená-los em um banco SQLite e interagir via um agente conversacional baseado em GPT-4o-mini para consultas e previsões sobre o índice de inflação brasileiro.

O **SQL_Agent** foi projetado para:

- **Coletar** dados históricos de IPCA diretamente do site do IBGE; 
- **Armazenar** em um banco de dados SQLite (`ipca.db`), garantindo consulta rápida e reproduzível;
- **Criar** um agente de IA (usando LangChain + OpenAI GPT-4o-mini) capaz de executar queries SQL no banco e gerar análises e previsões em português brasileiro.

# Funcionalidades

1. ipca_scraper.py:  
   - Raspa a tabela de IPCA do site da Ideal Softwares (dados oficiais do IBGE);  
   - Normaliza valores (de `','` para `'.'`) e armazena mês, ano e valor no SQLite.

2. Main.py:  
   - Carrega o banco `ipca.db` via `SQLDatabase` do LangChain;
   - Monta um toolkit SQL (`SQLDatabaseToolkit`) e um agente ReAct com GPT-4o-mini;
   - Executa consultas e previsões.
