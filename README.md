# Mitigation_2
# Estratégias para Mitigação do Viés de Confirmação em Grandes Modelos de Linguagem (LLMs)

Este repositório contém os scripts de automação e análise utilizados no projeto. O presente estudo visa analisar e comparar a eficácia de diversas técnicas de mitigação do viés de confirmação.

### Modelos Avaliados
A pesquisa concentrou-se na análise detalhada de quatro modelos principais, divididos nas seguintes categorias de inferência:

* **Comerciais (via API OpenRouter):** ChatGPT (GPT-4o), Claude (Anthropic) e DeepSeek.
* **Open-Source (via execução local no LM Studio):** Mistral.

## Como Executar os Experimentos

### 1. Configuração de Modelos via API (OpenRouter)
Este script automatiza a recolha de respostas para os modelos comerciais (**ChatGPT, Claude e DeepSeek**), sendo ideal para execução em ambientes como o Google Colab.

* **Chave API:** Localize a variável `api_key` ou `OPENROUTER_API_KEY` no script e insira a sua chave secreta do OpenRouter entre aspas.
* **Execução:** O script lê o ficheiro `.csv` de entrada, processa as perguntas e grava os resultados diretamente no ficheiro final correspondente (ex: `respostas_claude_exp9a16.csv`). Devido à integração da **retoma segura**, se a ligação cair, o código recomeça automaticamente a partir da última linha vazia.

### 2. Abordagem Multi-Agente (CrewAI - Experimento 14)
Para o ambiente de debate multi-agente (Redator vs. Advogado do Diabo) recorrendo às APIs do OpenRouter:
* **Prefixo Obrigatório:** É obrigatório incluir o prefixo `openrouter/` antes do identificador do modelo no parâmetro de inicialização (ex: `model="openrouter/anthropic/claude-4.6-sonnet"` ou `model="openrouter/openai/gpt-4o"`).
* **Gestão de Progresso:** O script utiliza o próprio ficheiro de output (`respostas_chatgpt_exp14_multiagente.csv`) como base de dados de leitura. Se o ficheiro já contiver linhas preenchidas, o CrewAI salta essas perguntas em milissegundos e retoma o debate exatamente na primeira linha em falta.

### 3. Configuração de Modelos Locais (LM Studio)
Este script faz a ponte com o modelo de código aberto (**Mistral**) executado localmente na sua máquina física, sem consumo de créditos.

* **No LM Studio:** Carregue o modelo **Mistral** e ative o servidor local clicando no botão de *Start Server* (verifique se a porta padrão `1234` está selecionada).
* **No Código (Início):** Certifique-se de que o URL do endpoint aponta corretamente para o ambiente local:
  ```python
  url = "http://localhost:1234/v1/chat/completions"

---

## Pré-requisitos e Instalação

Para replicar as experiências (especialmente recomendável o uso de ambientes como o Google Colab para os modelos via API), é necessário instalar as seguintes bibliotecas Python:

```bash
pip install pandas crewai



