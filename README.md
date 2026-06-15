# Mitigation_2
# Estratégias para Mitigação do Viés de Confirmação em Grandes Modelos de Linguagem (LLMs)

Este repositório contém os *scripts* de automação, processamento de dados e análise desenvolvidos para o projeto de estágio/final de curso. O estudo tem como principal objetivo analisar, testar e comparar a eficácia de diversas técnicas de *prompt engineering* e arquiteturas de modelos na redução do viés de confirmação em respostas médicas e nutricionais geradas por LLMs.

## Sobre o Projeto

O viés de confirmação em LLMs é um desafio crítico, especialmente em domínios sensíveis. Este projeto avalia desde abordagens de *zero-shot* e *few-shot* até sistemas mais complexos de debate **multi-agente** (utilizando a framework CrewAI), procurando responder à questão: *Como podemos forçar um modelo a considerar perspetivas alternativas antes de responder?*

### Modelos Avaliados
A pesquisa abrange um leque diversificado de modelos, divididos em duas categorias de inferência:

* **Comerciais (via API OpenRouter):** GPT-4o, Claude 3.5/4.6 Sonnet, Claude 3.7, Gemini 1.5 Pro, DeepSeek-V3, Qwen3-235B-A22B, Grok-3.
* **Open-Source (via execução local no LM Studio):** Meta-Llama-3.1-8B, Mistral-7B-v0.3, Qwen-2.5-7B, Gemma-3-4B.

---

## Pré-requisitos e Instalação

Para replicar as experiências (especialmente recomendável o uso de ambientes como o Google Colab para os modelos via API), é necessário instalar as seguintes bibliotecas Python:

```bash
pip install pandas crewai
