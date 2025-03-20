# Projeto de CNN com Otimização de Hiperparâmetros

Este repositório implementa uma rede neural convolucional (CNN) para classificação de imagens do conjunto CIFAR-10, com foco na otimização de hiperparâmetros utilizando Optuna. A arquitetura, embora simples, foi capaz de atingir resultados consistentes, graças à metodologia de busca e ao uso eficiente de recursos computacionais.

## Tecnologias Utilizadas

- **PyTorch:** Base para a implementação e treinamento das redes neurais.
- **PyTorch Lightning:** Framework que abstrai os detalhes do treinamento, oferecendo uma estrutura modular e escalável.
- **Optuna:** Biblioteca para otimização de hiperparâmetros, com suporte a técnicas de pruning para interromper treinamentos com desempenho insatisfatório.
- **torchvision:** Utilizada para facilitar o acesso e o pré-processamento dos dados do conjunto CIFAR-10.

## Descrição do Projeto

O projeto realiza as seguintes etapas:

1. **Pré-processamento dos Dados:**
   - Conversão das imagens para tensores.
   - Normalização dos dados para o intervalo [-1, 1] utilizando `transforms.Normalize`.
   - Divisão do conjunto CIFAR-10 em treino, validação e teste com seed fixa (42), garantindo reprodutibilidade.

2. **Definição da Arquitetura da CNN:**
   - Sequência de camadas convolucionais com opção de Batch Normalization.
   - Camada de pooling (MaxPool ou AvgPool) para redução dimensional.
   - Camadas totalmente conectadas (fully-connected) após o flatten dos recursos extraídos.

3. **Otimização dos Hiperparâmetros:**
   - Busca de configurações ideais para parâmetros como número de camadas, tamanho dos filtros, kernel size, taxa de aprendizado, dropout, entre outros.
   - Utilização do Optuna para explorar o espaço de busca dos hiperparâmetros e aplicar pruners para acelerar a busca em configurações subótimas.
   - Salvamento de checkpoints para o melhor modelo encontrado durante a otimização.

4. **Avaliação e Visualização:**
   - Avaliação final do modelo no conjunto de teste utilizando métricas de loss e acurácia.
   - Visualização dos resultados com gráficos de importância dos hiperparâmetros, histórico de otimização e matriz de confusão.
   - Exibição de exemplos de predições com comparativo entre os rótulos verdadeiros e os preditos.

## Estrutura do Projeto

- **projeto_cnn.ipynb:** Notebook que contém a implementação completa do projeto, desde o pré-processamento dos dados e definição do modelo até a otimização e avaliação final.
- **optuna_checkpoints/** e **optuna_cnn/**: Diretórios que armazenam os checkpoints dos modelos e os logs gerados durante a otimização.

## Conclusão

Esse projeto demonstra como combinar técnicas modernas de deep learning com a otimização automatizada de hiperparâmetros para resolver problemas de classificação de imagens. A abordagem adotada possibilita não só a obtenção de um modelo eficaz para o CIFAR-10, mas também fornece insights sobre a influência de cada hiperparâmetro no desempenho do modelo, servindo de base para estudos e aplicações futuras.
