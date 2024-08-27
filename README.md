# Dominando o ajuste fino de grandes modelos de linguagem

O ajuste fino melhora as capacidades dos LLMs pré-treinados, permitindo que eles aprendam novos conhecimentos específicos de um determinado domínio, assim, sabendo até mesmo conceitos/terminologias avançadas. Para isso será utilizado técnicas de ajuste fino com eficiência de parâmetros (**PEFT**), como **LoRA** e **QLoRA**.

**Código Completo**: [Dominando o ajuste fino de grandes modelos de linguagem](https://colab.research.google.com/drive/1x-0E9xwxe-VYdtt0MVOmP4MImULfpppu?usp=sharing)

## Conceitos
**LoRA**: Denominado como Low Rank Adaption, é um método que adiciona pequenos módulos de adaptação no modelo base e treina apenas os parâmetros provenientes desses módulos. Esses módulos adaptativos são matrizes bem menores comparadas com as dimensões dos módulos lineares base, logo além de conseguirem receber os mesmos prompts de entrada eles conseguem produzir uma saída compatível com a arquitetura existente, cedendo uma computação de parâmetros mais rápida do que as dos módulos originais do modelo.

**QLoRA** : Chamado de Quantized Low Rank Adaptation, é uma extensão do LoRa, ele irá adicionar uma camada de quantização no processamento dos parâmetros incrementados, reduzindo assim a quantidade de bits disponíveis para a armazenar os números que representam os parâmetros, gerando treinamentos mais rápidos e menos custosos computacionalmente (usando quantização sem sacrificar o desempenho). Para o nosso caso será adicionado uma quantização saindo de 32 bits para 4 bits, exigindo assim menos memória do modelo.

## Construção
Para esse projeto utilizou-se os seguintes componentes:

**Modelo** - Mistral 7B;

**Conjunto de dados** - Alpaca Dataset released;

**Treinamento e configurações** - Transformers;

**Ajuste fino com eficiência de parâmetros (PEFT)** - LoRA e QoRA;
