# 🚀 Claude Code Agent no Google Colab com Ollama

Este repositório contém uma adaptação para executar o **Claude Code** (código vazado) como um agente de IA no Google Colab, utilizando o **Ollama** de forma direta e gratuita.

---

## 🛠️ Como Funciona

Esta versão utiliza a compatibilidade nativa do Ollama com a API da OpenAI/Anthropic. Ao configurar as variáveis de ambiente corretamente, o Claude Code envia suas requisições diretamente para o servidor local do Ollama, eliminando a necessidade de proxies intermediários como o Bifrost.

---

## 🚀 Como Usar no Google Colab

Você pode abrir o notebook `claude_code_colab_agent.ipynb` diretamente no Google Colab para uma experiência guiada:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dragonbrxos/claude-code-agent-colab/blob/master/claude_code_colab_agent.ipynb)

### Passos Rápidos:

1.  **Instalação + Servidor Ollama:**
    ```bash
    !apt-get update -y && !apt-get install -y zstd curl
    !curl -fsSL https://ollama.com/install.sh | sh
    !nohup /usr/local/bin/ollama serve > ollama.log 2>&1 &
    ```

2.  **Preparar o Agente:**
    ```bash
    !git clone https://github.com/dragonbrxos/claude-code-agent-colab.git
    !cd claude-code-agent-colab && npm install && npm run build
    ```

3.  **Configurar o Modelo (Funções Python):**
    Agora você pode escolher entre o modelo padrão ou um customizado:
    ```python
    # Para o modelo padrão (Llama3:8b):
    configurar_modelo_padrao()

    # Para qualquer outro modelo (ex: mistral, llama3.1, etc):
    configurar_modelo_customizado("mistral")
    ```

4.  **Rodar o Agente:**
    ```bash
    !cd claude-code-agent-colab && node dist/main.js
    ```

---

## 💡 Vantagens desta Versão

*   **Flexibilidade:** Alterne entre modelos facilmente usando funções Python.
*   **Simplicidade:** Sem necessidade de configurar o Bifrost ou proxies complexos.
*   **Estabilidade:** Utiliza o método de instalação oficial do Ollama que funciona perfeitamente no ambiente do Colab.

---

## ⚠️ Observações

*   Recomenda-se o uso de um runtime com **GPU** no Colab para uma resposta mais rápida do modelo.
*   O ambiente do Colab é temporário; se o runtime for reiniciado, os passos de instalação devem ser repetidos.

---

## 📄 Créditos

Esta adaptação foi criada para facilitar o uso de agentes de IA locais em ambientes de nuvem gratuitos.
