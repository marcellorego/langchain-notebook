# Introdução a Generative AI, LLMs e desenvolvimento com LangChain

Bem-vindo ao repositório LangChain Notebook! Este repositório contém todos os exemplos de código que você precisará acompanhar junto com a apresentacao disponivel no arquivo PDF abaixo. 
Ao final deste curso, você saberá como usar LangChain para criar seus próprios agentes de IA, construir chatbots RAG e automatizar tarefas com IA.

[Gen AI e LangChain.pdf](https://github.com/marcellorego/langchain-notebook/blob/main/Gen AI e LangChain.pdf)


## Implementação prática em Python

1. **Setup Environment**
2. **Chat Models**
3. **Prompt Templates**
4. **Chains**
5. **RAG (Retrieval-Augmented Generation)**
6. **Agents & Tools**

## Passos para execução

### Pre-requisitos

- Python >= 3.10 (https://www.python.org/)
- Docker (https://www.docker.com/)
- Docker-compose (https://docs.docker.com/compose/install/)
- python3.10-venv
- pip
- terminal do SO

### Instalação

1. Clonar o repositório:

   ```bash
   git clone git@github.com:marcellorego/langchain-notebook.git
   cd langchain-notebook
   ```

2. Executar LLM localmente

A utilização da LLM localmente sera feita com o modelo [Ollama](https://github.com/ollama/ollama)
Com a execução do comando abaixo, o modelo sera baixado usando docker, e uma versão do modelo mais atualizad tambem será baixada.
Este comando define um perfil de execução, o qual utiliza a CPU como principal núcleo de processamento.

  ```bash
  docker-compose -f docker-compose/docker-compose-ollama.yaml --profile cpu up
  ```

3. Executar Jupyterlab notebook

  * Criar ambiente Python virtual (https://docs.python.org/pt-br/3.10/library/venv.html). Vamos chamá-lo de `.venv`.
  
  ```bash
  python3 -m venv .venv
  ```

  * Ativar o ambiente virtual
  ```bash
  source ./.venv/bin/activate
  ```

  * Instalar as dependências e módulos necessarios para execução do Jupyterlab notebook
  ```bash
  pip install -r requirements.txt
  ```

  * Executar Jypyterlab notebook
  ```bash
  ./.venv/bin/jupyter notebook
  ```

  * Navegação pela aplicação
  Caso o navegador não abra com a aplicação, veja no terminal se há alguma mensagem tal como abaixo, e siga o link indicado.
  `Or copy and paste one of these URLs: ...`

  * Python notebooks de exemplo estão mantidos na pasta `notebooks`

4. Para desativar Jupyterlab notebook, basta pressionar CTRL+C

5. Para desativar o ambiente virtual
  ```bash
  deativate
  ```

6. Para desativar o modelo LLM
  ```bash
  docker-compose -f docker-compose/docker-compose-ollama.yaml down
  ```


## Referências
https://medium.com/@laquesisa/virtual-environment-in-jupyter-lab-8b3815ba9662
https://medium.com/@claudia.nikel/how-to-setup-a-jupyter-notebook-in-vs-code-w-virtual-env-kernels-install-packages-884cf643375e
https://jupyter.org/