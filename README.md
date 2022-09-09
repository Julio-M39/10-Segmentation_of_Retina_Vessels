# Segmentation of Retina Vessels

### Segmentação dos Vasos da Retina

### Definição do Projeto

<div>
<img src="https://user-images.githubusercontent.com/54995990/189434093-f1f51e67-e528-4792-947e-b03ddaba5182.png" width="700px" />
</div>

A detecção e análise automáticas da vasculatura podem auxiliar na implementação de programas de rastreamento para retinopatia diabética, podem auxiliar na pesquisa sobre a relação entre a tortuosidade do vaso e a retinopatia hipertensiva, medição do diâmetro do vaso em relação ao diagnóstico de hipertensão e cirurgia a laser assistida por computador. A geração automática de mapas retinais e extração de pontos de ramificação têm sido usados para registro de imagens temporais ou multimodais e síntese de mosaico de imagens retinais.

Usaremos uma estrutura modificada da arquitetura U-Net com o objetivo de alcançar resultados próximos ao estado da arte em IA para imagens médica.

**Referências:**

<a href="https://arxiv.org/abs/1505.04597">U-Net: Convolutional Networks for Biomedical Image Segmentation</a>

<a href="https://ieeexplore.ieee.org/abstract/document/8589312">Weighted Res-UNet for High-Quality Retina Vessel Segmentation</a>

### Base de Dados

O conjunto de dados consiste em 40 imagens do globo ocular anotadas por especialistas, divididas igualmente em um conjunto de treinamento e teste de 20 imagens cada. Cada imagem foi capturada usando 8 bits por plano de cor em 768 por 584 pixels. O FOV (Field of View) de cada imagem é circular com um diâmetro de aproximadamente 540 pixels. Para este conjunto de dados, as imagens foram cortadas ao redor do FOV. Para cada imagem, é fornecida uma imagem de máscara que delineia o FOV.

**Fonte:**

https://drive.grand-challenge.org/

### Etapas do Projeto

- Carregando os Dados (Imagens e Máscaras)
- Preparação dos Geradores de Dados
- Aumento de Dados
- Pipeline de Dados
- U-Net++
- Função de Erro, Métricas e Compilação do Modelo
- Treinamento
- Avaliação

### Resultados

| IOU  | AUC | Precision | Recall | F1-Score | Sensitivity | Specificity |
| ---- | --- | --------- | ------ | -------- | ----------- | ----------- |
| 76%  | 92% |    86%    |   86%  | 86%      | 86%         | 97%         |

Na figura abaixo temos os resultados visuais obtidos pelo modelo de segmentação, na primeira linha temos as imagens da base de dados, na segunda linha temos as máscaras originais, e por fim na terceira e ultima linha temos as máscaras feitas pelo modelo de segmentação.
 
<div>
<img src="https://user-images.githubusercontent.com/54995990/189438017-68e83508-35c6-4bba-9f1b-42c3c352d0f7.png" width="700px" />
</div>
