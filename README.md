# IDENTIFICAÇÃO DE FOGO EM IMAGENS UTILIZANDO TÉCNICAS DE CLASSIFICAÇÃO

Um problema de visão computacional que utiliza uma abordagem de aprendizado supervisionado para classificar imagens de acordo com a presença e ausência de fogo.

- **Descrição da base de dados:** A base de dados possui imagens com e sem fogo ao ar livre para tarefas de visão computacional. Ao todo são 999 imagens, onde 755 são de fogo ao ar livre podendo apresentar fumaça densa, e 244 não são de fogo e podem apresentar grama, estradas, árvores, florestas, lagos, rios, cachoeiras, animais e pessoas. 


- **Link da base de dados original:** https://www.kaggle.com/datasets/phylake1337/fire-dataset
> O diretório `content/fire_dataset` contém as imagens originais disponibilizadas no kaggle.

<br> 

## Descrição dos atributos da base de dados após pré-processamento

> Os pixels e os histogramas das imagens foram extraídos apenas para imagens que possuem 3 canais de cores.

| Nome do atributo | Descrição | Tipo |
|------------------|-----------|------|
| image_path | Caminho para a imagem a partir do diretório fire_dataset | STRING |
| label | Representação numérica da classe da imagem. Pode assumir os valores abaixo para imagens sem fogo e com fogo, respectivamente: <br> - 0  <br> - 1 | INTEGER |
| label_name | Representação textual da classe da imagem. Pode assumir os valores: <br> - Sem fogo <br> - Com fogo | STRING |
| source_shape | Shape da imagem original | STRING |
| source_height | Altura da imagem original | FLOAT |
| source_width | Largura da imagem original | FLOAT |
| source_channel | Quantidade de canais de cores da imagem original | FLOAT |
| pixel0 à pixel29999 | Pixels da imagem redimensionada | FLOAT |
| hist_b_0 à hist_b_255 | Bins do histograma de intensidade do canal de cor azul da imagem redimensionada | FLOAT |
| hist_g_0 à hist_g_255 | Bins do histograma de intensidade do canal de cor verde  da imagem redimensionada | FLOAT |
| hist_r_0 à hist_r_255 | Bins do histograma de intensidade do canal de cor vermelho da imagem redimensionada | FLOAT |

## Descrição dos arquivos gerados após pré-processamento

Para cada etapa do pré-processamento foram gerados arquivos com o dataset modificado para permitir a reprodução do experimento a partir do ponto desejado. Os arquivos gerados estão presentes no diretório `content/data` no formato `csv`. Abaixo a descrição de cada arquivo.

- `images_full_dataset.csv`: contém os atributos listados acima de todas as imagens presente no dataset original.
- `images_dataset.csv`: contém os atributos listados acima das imagens que são utilizadas no experimento, ou seja, são utilizadas apenas as imagens que possuem 3 canais de cores.

Os arquivos abaixo possuem origem do dataset presente no arquivo `images_dataset.csv`. É importante destacar que os arquivos utilizados para o treinamento e teste dos modeos estão presentes no diretório processed.
- `sample.csv`: contém uma amostra de 10 imagens do datatase, sendo 5 de cada classe.
- `train_images.csv`: contém o conjunto de imagens utilizada no treinamento dos algoritmos.
- `train_images_albumentation.csv`: contém as mesmas imagens presentes no conjunto de treinamento, porém com albumentation aleatório. Esse dataset pode ser somado ao `train_images.csv` para realizar o treinamento dos algoritmos.
- `train_images_noise.csv`: contém as mesmas imagens presentes no conjunto de treinamento, porém com ruído aleatório. Esse dataset pode ser somado ao `train_images.csv` para realizar o treinamento dos algoritmos.
- `valid_images.csv`: contém o conjunto de imagens utilizadas para validação.
- `test_images.csv`: contém o conjunto de imagens utilizadas para teste.
