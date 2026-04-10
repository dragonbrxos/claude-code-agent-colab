# 🟢 Claude Code Agent - Google Colab Edition

Este repositório contém uma versão adaptada do **Claude Code Agent** para rodar 100% no **Google Colab** usando o modelo **Llama3:8b** via **Ollama**.

## 🚀 Como Usar no Google Colab

1. Abra o arquivo `claude_code_colab_agent.ipynb` no seu Google Colab.
2. Execute as células em ordem:
   - **Célula 1**: Instala o Ollama e inicia o servidor.
   - **Célula 2**: Baixa o modelo `llama3:8b`.
   - **Célula 3**: Prepara o ambiente e inicia o agente.

## 🧹 Instalação e Execução (Bloco Único)

Se você quiser rodar tudo em uma única célula de código no Colab, copie e cole o bloco abaixo:

```bash
# 1. Limpar instalação antiga e clonar a nova versão
!rm -rf claude-code-agent-colab
!git clone https://github.com/dragonbrxos/claude-code-agent-colab.git

# 2. Configurar ambiente para 100% de compatibilidade
import os
os.environ['ANTHROPIC_BASE_URL'] = 'http://localhost:11434/v1'
os.environ['ANTHROPIC_API_KEY'] = 'ollama-key'
os.environ['CLAUDE_CODE_SIMPLE'] = '1'
os.environ['DISABLE_TELEMETRY'] = '1'
os.environ['FORCE_COLOR'] = '1'
os.environ['TERM'] = 'xterm-256color'
os.environ['NODE_OPTIONS'] = '--max-old-space-size=4096'

# 3. Instalar dependências, fazer o build e iniciar o agente
!cd claude-code-agent-colab && npm install --no-audit --no-fund --quiet && npm run build && npm start
```

## 🛠️ O que foi adaptado?

- **TTY Emulation**: Forçado suporte a cores e terminal interativo para o ambiente do Colab.
- **Llama3 Integration**: O modelo `llama3:8b` foi injetado como o modelo padrão no código-fonte.
- **No Auth**: Removida a necessidade de chaves da Anthropic (usa Ollama local).
- **Memory Optimization**: Configurado Node.js para usar até 4GB de RAM para evitar crashes.
- **No Telemetry**: Desativada toda a telemetria da Anthropic para maior privacidade e velocidade.

---
Adaptado por Manus AI para dragonbrxos.
