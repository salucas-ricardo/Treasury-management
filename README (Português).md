---
# Treasury-Management (Gestão de Tesouraria)
**Automação de operações financeiras:** Scripts e utilitários para reconciliação de contas, gestão de livros razão (ledgers), previsão geral (forecast) e processamento de dados financeiros.

# Finance Operations Toolkit
Este toolkit foi desenvolvido com a lógica de **ERP (Enterprise Resource Planning)** em mente, pensado para ajudar no ajuste, escrita de dados e previsões, facilitando a integração direta com dashboards de **Power BI**.

## 🛠 Funcionalidades
  * **Gestão de Ledger:** Ferramentas para atualizações em massa e verificações de integridade de dados.
  * **Previsão (Forecasting):** Scripts para análise de tendências e projeções orçamentais.
  * **Processamento de Dados:** Utilitários ETL para limpar e transformar exportações financeiras brutas.

## 📦 Instalação e Requisitos
Para que este script funcione, deverás instalar as seguintes bibliotecas na tua plataforma (Terminal/Prompt):
```bash
pip install pandas numpy openpyxl xlsxwriter faker

```

### Importação de Bibliotecas (Bíblias)
O script utiliza as seguintes dependências internas:
* `pandas`, `numpy`, `re` (Regex), `faker`, `datetime`, `openpyxl`, `xlsxwriter`, `shutil`, entre outras.

---

## ⚠️ AVISO IMPORTANTE
**Não remova qualquer parte do código do script.** Se o fizeres, poderás interromper a lógica de automação e comprometer a integridade dos dados.

---

## ⚙️ Configuração Personalizada
No campo **"CÓDIGOS AUXILIARES"**, podes alinhar as regras às tuas necessidades. Exemplos:
  * **Substituição de Termos:** Alterar `RECEITA` e `DESPESA` para `REVENUE` e `LIABILITIES`.
  * **Dados Bancários:** Atualizar para outros bancos conforme a tua realidade.
  * **Entidades:** É possível inserir os fornecedores/clientes que precisares.

*Nota: Não é recomendado alterar o nome do ficheiro de relatório `Relatório Financeiro 100k.xlsx` para evitar erros de leitura.*

---

## 🚀 Passos Operacionais (Fluxo de Trabalho)
  1. **Decisão de Módulo:** Escolhe se pretendes trabalhar com `RECEITA` ou `DESPESA` (podes escrever em minúsculas).
  2. **Filtragem de Período:** Escolhe o período de trabalho. Se necessário, podes clicar em `+ CODE` abaixo do script e escrever `sheet` para visualizar o que foi processado até ao momento.
  3. **Gestão e Forecast:** Antes de realizar a previsão, deves decidir se queres:
  * `[a]dicionar`: Nova linha.
  * `[e]ditar`: Trabalhar na última entrada.
  * `[u]ltima`: Reajustar uma linha específica através do índice.
  4. **Edição de Colunas:** Podes escolher qualquer coluna para trabalhar e escrever nela, exceto as colunas proibidas (bloqueadas para manter a integridade). Se tentares uma proibida, o script não permitirá a alteração.
  5. **Ajuste de DFC (Demonstrativo de Fluxo de Caixa Diário):**
  * Define o dia desejado no formato **"AAAA-MM-DD"**.
  * Escolhe entre as opções: `[0] Conta Garantida - Limite` ou `[1] Transferências Recebido e Enviado`.
  * Se escolheres `[1]`, surgirão as opções bancárias onde deverás inserir o número que representa a conta.
  * Insere os valores na caixa correspondente.


6. **Finalização e Formatação:** O script irá formatar os dados, enviar para a base de dados, criar as folhas (sheets) para os 3 dias seguintes (ignorando fins de semana e feriados) e gerar um ficheiro resumido para partilha com a equipa (14 DFCs se antes do meio do mês, ou 30 dias se após o meio do mês).

---

## 📊 Formatos de Dados
  * **DATAS e VALORES:** Formatação standard para processamento financeiro.
  * **NÚMERO DAS CONTAS:** Identificação numérica das contas bancárias.
  * **CATEGORIZAR (DESPESAS):** Operacionais, Financeiras, Fiscais e Outras Despesas.
  * **CATEGORIZAR (RECEITAS):** Receita, Estorno, Devolução e Empréstimos.
  * **ATUALIZAÇÃO:** Processamento automático dos DFCs.

---

Este repositório é a ferramenta ideal para garantir que os dados chegam ao **Power BI** de forma limpa, padronizada e já com lógica de previsão aplicada.
