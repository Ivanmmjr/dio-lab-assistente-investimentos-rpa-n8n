# 📊 Assistente de Investimentos com RPA, n8n e IA Generativa

Repositório desenvolvido para a conclusão do **Desafio Completo** da Digital Innovation One (DIO), integrando automação de processos via Python (RPA), fluxos low-code e inteligência artificial generativa.

---

## 🚀 Arquitetura e Fluxo da Solução

1. **Camada de Extração (RPA em Python):**
   * Utiliza a biblioteca `BeautifulSoup` para raspar os dados da tabela de clientes hospedada no GitHub Pages (Nome, E-mail, Saldo e Perfil de Risco).
   * Envia os dados estruturados em lote via requisição `HTTP POST` para o Webhook do n8n.

2. **Camada de Orquestração e Processamento (n8n):**
   * **Webhook:** Recebe os dados enviados pelo script Python.
   * **Item Lists (Split Out):** Separa a lista recebida para processar cada cliente individualmente.
   * **HTTP Request:** Lê o arquivo `data.csv` com as opções de investimento oficiais.
   * **Agente de IA (LLM / Google Gemini):** Cruza os dados do cliente e do CSV para gerar uma recomendação de investimento dinâmica, humanizada e personalizada.

---

## 🛠️ Decisões Técnicas

* **Simulação de Operador (RPA):** O uso do BeautifulSoup substitui a necessidade de APIs fechadas, extraindo dados de páginas web de forma automatizada.
* **Desacoplamento por Webhook:** O envio assíncrono via POST garante que a extração ocorra de forma fluida antes de passar pelo motor de IA.
* **Geração Dinâmica via LLM:** Substituição de regras estáticas por inteligência artificial generativa para adaptar o tom da consultoria e o volume de saldo de cada cliente de maneira inteligente.
