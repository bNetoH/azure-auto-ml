# Machine Learning Automatizado no Azure - DIO.me [Laboratorio M01 PT01]

## Visão Geral

O desafio é replicar o projeto do Machine Learning Automatizado no Azure Machine Learning para treinar e avaliar um modelo preditivo. O objetivo é prever o número de aluguéis de bicicletas em um determinado dia, com base em características sazonais e meteorológicas.

## Pré-requisitos

- Assinatura ativa do Microsoft Azure. [https://azure.microsoft.com](https://azure.microsoft.com).

## Etapas para Execução

### 1. Criação de um Workspace do Azure Machine Learning

1. **Acessar o Portal do Azure**: Faça login no [Portal do Azure](https://portal.azure.com).
2. **Criar um novo recurso de Machine Learning**:
   - Criar um recurso e pesquise por "Machine Learning".
   - Selecione "Azure Machine Learning" e clique em "Criar".
   - Preencha os seguintes campos:
     - **Assinatura**: Selecione sua assinatura do Azure.
     - **Grupo de Recursos**: Crie ou selecione um grupo de recursos existente.
     - **Nome**: Forneça um nome exclusivo para o workspace.
     - **Região**: Escolha "Leste dos EUA" ou outra região disponível.
   - Mantenha as demais padrão e clique em "Revisar + criar".
   - Após a validação, clique em "Criar" e aguarde a implantação ser concluída.
3. **Lançar o Azure Machine Learning Studio**:
   - Após a criação do workspace, clique em "Ir para o recurso".
   - No painel do workspace, clique em "Lançar estúdio" para abrir o [Azure Machine Learning Studio](https://ml.azure.com).

### 2. Uso do Machine Learning Automatizado para Treinar um Modelo

1. **Acessar a seção de ML Automatizado**:
   - No Azure Machine Learning Studio, navegue até "Automated ML" no menu lateral.
2. **Criar um novo trabalho de ML Automatizado**:
   - Clique em "Novo trabalho de Automated ML".
   - Configurações básicas:
     - **Nome do trabalho**: Mantenha o nome padrão ou forneça um novo.
     - **Nome do experimento**: `mslearn-bike-rental`
     - **Descrição**: `Automated machine learning for bike rental prediction`
3. **Selecionar o tipo de tarefa e conjunto de dados**:
   - **Tipo de tarefa**: Selecione "Regressão".
   - **Conjunto de dados**:
     - Clique em "Criar novo conjunto de dados" e selecione "A partir de arquivos locais".
     - Faça o upload dos arquivos de dados históricos de aluguel de bicicletas disponíveis em [https://aka.ms/bike-rentals](https://aka.ms/bike-rentals).
     - Nomeie o conjunto de dados como `bike-rentals` e forneça uma descrição adequada.
4. **Configurar as definições da tarefa**:
   - **Coluna alvo**: Selecione `rentals` (inteiro).
   - **Métrica primária**: `NormalizedRootMeanSquaredError`
   - **Modelos permitidos**: Selecione apenas `RandomForest` e `LightGBM` para reduzir o tempo de execução.
   - **Limites**:
     - **Máximo de testes**: `3`
     - **Máximo de testes simultâneos**: `3`
     - **Máximo de nós**: `3`
     - **Limite de pontuação da métrica**: `0.085`
5. **Iniciar o trabalho**:
   - Revise todas as configurações e clique em "Iniciar" para executar o trabalho de ML Automatizado.
   - Aguarde a conclusão do trabalho e analise os resultados para identificar o melhor modelo treinado.

## Limpeza de Recursos

Após a conclusão do projeto, para evitar custos adicionais:

1. No [Portal do Azure](https://portal.azure.com), navegue até o grupo de recursos que contém o workspace do Machine Learning.
2. Selecione o grupo de recursos e clique em "Excluir grupo de recursos".
3. Confirme a exclusão digitando o nome do grupo de recursos e clicando em "Excluir".

## Link do desafio

- [Explorar o Machine Learning Automatizado no Azure Machine Learning](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html)
