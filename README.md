# YOLOv4 - Treinamento e Teste

Este projeto demonstra como criar uma base de dados, configurar e treinar uma rede **YOLOv4** para detecção de objetos utilizando o **Google Colab**.

## 🚀 Passos principais

1. **Configuração do ambiente**

   * Clonar o repositório do Darknet.
   * Compilar com suporte a GPU (ou CPU, se necessário).

2. **Base de dados**

   * Pode-se usar uma base própria (rotulada com LabelMe) ou utilizar datasets já anotados, como o **COCO**.
   * As imagens são divididas em treino (80%) e teste (20%).

3. **Arquivos de configuração**

   * `obj.data`: define os caminhos de treino/teste, classes e backup.
   * `obj.names`: lista das classes a serem detectadas.
   * `yolov4-2classes.cfg`: configuração da rede adaptada para o número de classes.

4. **Treinamento**

   ```bash
   !./darknet detector train data/obj.data cfg/yolov4-2classes.cfg yolov4.conv.137 -dont_show -map
   ```

5. **Teste**

   ```bash
   !./darknet detector test data/obj.data cfg/yolov4-2classes.cfg backup/yolov4-2classes_final.weights data/obj/images/example.jpg -thresh 0.25
   ```

## 📂 Estrutura do Projeto

```
├── data/
│   ├── obj.data        # Caminhos para treino/teste
│   ├── obj.names       # Nomes das classes
│   ├── train.txt       # Lista de imagens de treino
│   ├── test.txt        # Lista de imagens de teste
│   └── obj/images/     # Imagens de treino e teste
├── cfg/
│   └── yolov4-2classes.cfg
└── backup/             # Pesos salvos durante o treino
```

## 🛠 Requisitos

* Google Colab (recomendado GPU habilitada)
* Darknet YOLOv4
