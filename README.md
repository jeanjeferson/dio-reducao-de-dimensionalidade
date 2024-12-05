# Redução de Dimensionalidade em Imagens para Redes Neurais

## Descrição do Projeto
Este projeto implementa técnicas de processamento de imagens para redução de dimensionalidade, visando a preparação de dados para redes neurais. O código realiza a conversão de imagens coloridas para escalas de cinza e binarização, utilizando Python e bibliotecas de processamento de imagem.

## Funcionalidades

### 1. Conversão para Níveis de Cinza (Grayscale)
- Converte imagens RGB para escala de cinza (0 a 255)
- Utiliza o método de luminosidade com a fórmula: 0.299R + 0.587G + 0.114B
- Mantém as dimensões originais da imagem
- Reduz a complexidade da imagem de 3 canais para 1 canal

### 2. Binarização de Imagem
- Converte imagens em escala de cinza para formato binário (preto e branco)
- Utiliza um valor de limiar (threshold) padrão de 128
- Pixels acima do limiar se tornam brancos (255)
- Pixels abaixo do limiar se tornam pretos (0)

## Requisitos

- Python 3.x
- Bibliotecas:
  - PIL (Python Imaging Library)
  - OpenCV (cv2)

## Instalação

1. Clone o repositório:
```bash
git clone [url-do-repositório]
```

2. Instale as bibliotecas necessárias:
```bash
pip install pillow
pip install opencv-python
```

## Como Usar

### Conversão para Escala de Cinza

```python
from PIL import Image

# Converter imagem para escala de cinza
imagem_cinza = to_grayscale("caminho/da/imagem.jpg")
imagem_cinza.save("dataset/grayscale_imagem.jpg")
```

### Binarização

```python
# Converter imagem para preto e branco
imagem_binaria = binarize_image("caminho/da/imagem.jpg", threshold=128)
imagem_binaria.save("dataset/binarized_imagem.jpg")
```

## Detalhamento das Funções

### `to_grayscale(image_path)`
Converte uma imagem RGB para escala de cinza.

Parâmetros:
- `image_path`: Caminho da imagem de entrada

Retorno:
- Objeto PIL Image em formato grayscale

### `binarize_image(image_path, threshold=128)`
Converte uma imagem para formato binário.

Parâmetros:
- `image_path`: Caminho da imagem de entrada
- `threshold`: Valor de limiar (0-255) para conversão binária (padrão: 128)

Retorno:
- Objeto PIL Image em formato binário

## Tratamento de Erros

As funções incluem tratamento para:
- FileNotFoundError: Quando o arquivo de imagem não é encontrado
- Exceções gerais: Para outros erros potenciais durante o processamento

## Estrutura de Saída

As imagens processadas são salvas no diretório especificado:
- Imagens em escala de cinza: `dataset/grayscale_[nome_arquivo].jpg`
- Imagens binarizadas: `dataset/binarized_[nome_arquivo].jpg`

## Contribuição

Sinta-se à vontade para sugerir melhorias, criar issues ou enviar pull requests.

---

## Desafio Original

Este projeto foi desenvolvido como resposta ao seguinte desafio:

> Redução de Dimensionalidade em Imagens para Redes Neurais
> 
> Seguindo o exemplo do algoritmo de binarização apresentado em aula, realize a implementação em Python para transformar uma imagem colorida para níveis de cinza (0 a 255) e para binarizada (0 e 255), preto e branco.