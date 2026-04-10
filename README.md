# 🚀 Claude Code Agent no Google Colab com Ollama (Llama3:8b)

Este repositório contém uma adaptação para executar o **Claude Code** (código vazado) como um agente de IA no Google Colab, utilizando o modelo **Llama3:8b** através do **Ollama** de forma direta e gratuita.

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
    apt-get update -y && apt-get install -y zstd curl
    curl -fsSL https://ollama.com/install.sh | sh
    nohup /usr/local/bin/ollama serve > ollama.log 2>&1 &
    ```

2.  **Baixar o Modelo:**
    ```bash
    ollama pull llama3:8b
    ```

3.  **Preparar o Agente:**
    ```bash
    git clone https://github.com/dragonbrxos/claude-code-agent-colab.git
    cd claude-code-agent-colab
    npm install && npm run build
    ```

4.  **Configurar e Rodar:**
    ```python
    import os
    os.environ['ANTHROPIC_BASE_URL'] = 'http://localhost:11434/v1'
    os.environ['ANTHROPIC_API_KEY'] = 'ollama'
    os.environ['CLAUDE_MODEL'] = 'llama3:8b'
    # Executar: node dist/main.js
    ```

---

## 💡 Vantagens desta Versão

*   **Simplicidade:** Sem necessidade de configurar o Bifrost ou proxies complexos.
*   **Estabilidade:** Utiliza o método de instalação oficial do Ollama que funciona perfeitamente no ambiente do Colab.
*   **Performance:** Conexão direta reduz a latência entre o agente e o modelo.

---

## ⚠️ Observações

*   Recomenda-se o uso de um runtime com **GPU** no Colab para uma resposta mais rápida do modelo.
*   O ambiente do Colab é temporário; se o runtime for reiniciado, os passos de instalação devem ser repetidos.

---

## 📄 Créditos

Esta adaptação foi criada para facilitar o uso de agentes de IA locais em ambientes de nuvem gratuitos.
