# Claude Code como Agente de IA no Google Colab com LLM Gratuito (Llama3 via Ollama e Bifrost)

Este repositório contém uma versão adaptada do código-fonte vazado do Claude Code, configurado para ser executado como um agente de IA no Google Colab. O objetivo é permitir que o Claude Code, originalmente projetado para interagir com a API da Anthropic, utilize um Large Language Model (LLM) gratuito e de código aberto (Llama3) através do Ollama e do Bifrost como proxy, sem a necessidade de modificar o código-fonte original do Claude Code.

## Visão Geral do Projeto

O Claude Code é uma interface de linha de comando (CLI) de codificação de IA desenvolvida pela Anthropic. Esta adaptação permite explorar sua arquitetura e funcionalidades com um LLM gratuito, tornando-o acessível para pesquisa e experimentação sem custos de API.

## Como Usar no Google Colab (Plug-and-Play)

Para executar este agente de IA no Google Colab, siga estes passos simples:

1.  **Abra o Notebook no Google Colab:**
    Clique no link abaixo para abrir o notebook `claude_code_colab_agent.ipynb` diretamente no Google Colab:
    [https://colab.research.google.com/github/dragonbrxos/claude-code-agent-colab/blob/master/claude_code_colab_agent.ipynb](https://colab.research.google.com/github/dragonbrxos/claude-code-agent-colab/blob/master/claude_code_colab_agent.ipynb)

2.  **Execute as Células em Ordem:**
    Dentro do notebook, execute cada célula de código sequencialmente. O notebook foi projetado para automatizar todo o processo:
    *   Instalação do Node.js e Ollama.
    *   Download do modelo Llama3 no Ollama.
    *   Instalação e inicialização do Bifrost (que atuará como um proxy).
    *   Clonagem deste repositório do Claude Code.
    *   Instalação das dependências do Claude Code.
    *   Configuração das variáveis de ambiente para que o Claude Code se comunique com o Bifrost/Ollama.
    *   Execução do Claude Code.

### Observações Importantes:

*   **Recursos do Colab:** A execução de um LLM como Llama3 via Ollama no Colab pode consumir muitos recursos (RAM e GPU). Recomenda-se usar um ambiente de runtime com recursos adequados (por exemplo, Colab Pro ou um runtime com GPU).
*   **Persistência:** O ambiente do Colab é efêmero. Se o runtime for reiniciado, você precisará executar os passos novamente.
*   **Funcionalidades:** Nem todas as funcionalidades do Claude Code podem funcionar perfeitamente com um LLM genérico, pois ele foi otimizado para os modelos da Anthropic e suas ferramentas específicas. Testes serão necessários para verificar a compatibilidade total.

## Arquitetura e Adaptação

Esta adaptação utiliza o [Bifrost](https://github.com/maximhq/bifrost) como um gateway LLM. O Bifrost intercepta as chamadas de API que o Claude Code faria para a Anthropic e as redireciona para um LLM local (Llama3) executado via [Ollama](https://ollama.com/). Isso é feito configurando apenas algumas variáveis de ambiente, sem alterar o código-fonte original do Claude Code.

```text
Claude Code  -->  Bifrost (localhost:8080)  -->  Ollama (Llama3)
```

## Créditos e Licença

*   **Código Original do Claude Code:** Propriedade da Anthropic PBC. Este repositório é para fins educacionais e de pesquisa, não sendo um produto oficial da Anthropic.
*   **Descoberta do Vazamento:** Chaofan Shou (@Fried_rice).
*   **Adaptação e Configuração:** Manus AI.
*   **Ferramentas Utilizadas:** [Bifrost](https://github.com/maximhq/bifrost) e [Ollama](https://ollama.com/).

Este projeto é licenciado sob a licença MIT, conforme o `package.json` gerado para a adaptação.
