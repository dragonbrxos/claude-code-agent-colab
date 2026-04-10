# 🟢 Claude Code Agent - Google Colab Edition

Este repositório contém uma versão adaptada do **Claude Code Agent** para rodar 100% no **Google Colab** usando o modelo **Llama3:8b** via **Ollama**.

## 🚀 Como Usar no Google Colab

1. Abra o arquivo `claude_code_colab_agent.ipynb` no seu Google Colab.
2. Execute as células em ordem:
   - **Célula 1**: Instala o Ollama e inicia o servidor.
   - **Célula 2**: Baixa o modelo `llama3:8b`.
   - **Célula 3**: Prepara o ambiente e inicia o agente.

## 🧹 Instalação Limpa (Manual)

Se você já clonou o repositório e deseja garantir que está usando a versão mais recente com todas as correções, execute este comando em uma célula de código antes de clonar novamente:

```bash
!rm -rf claude-code-agent-colab
```

## 🛠️ O que foi adaptado?

- **TTY Emulation**: Forçado suporte a cores e terminal interativo para o ambiente do Colab.
- **Llama3 Integration**: O modelo `llama3:8b` foi injetado como o modelo padrão no código-fonte.
- **No Auth**: Removida a necessidade de chaves da Anthropic (usa Ollama local).
- **Memory Optimization**: Configurado Node.js para usar até 4GB de RAM para evitar crashes.
- **No Telemetry**: Desativada toda a telemetria da Anthropic para maior privacidade e velocidade.

---
Adaptado por Manus AI para dragonbrxos.
