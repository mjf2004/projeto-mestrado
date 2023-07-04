# projeto-mestrado
Detecção de máscara com os algoritmos de detecção Faster-RCNN, SSD e YOLO. O projeto de mestrado iniciado em 2020 e concluído em 2023.

Neste projeto foram usados nove modelos pré-treinados de redes neurais e três algoritmos de detecção de objetos Faster R-CNN, SSD e YOLO.

# Recursos:
Frameworks utilizados: Tensorflow API Object Detection e Darknet.

Dataset: Prajana dataset rotulado em português brasileiro.

Modelos pré-treinados comparados: Faster R-CNN Resnet 50, Faster R-CNN Resnet 101, Faster Inception-Resnet-V2, SSD Mobilenet V2, SSD Mobilenet V2 FPNLite, SSD Resnet 50 V1 FPN, YOLOv2, YOLOv3 e YOLOv4.

Google drive com os arquivos disponibilizados de forma púlica: bit.ly/3CS0FfZ.


O hardware considerado para todos os experimentos, tanto para o treinamento e avaliação, quanto para a inferência são as seguintes: 2 Processadores Intel(R) Xeon(R) CPU @ 2.20GHz, 25 GB de memória RAM e placa de vídeo Tesla P100-PCIE; informações retiradas no terminal do Google Colaboratory.

No arquivo "Descrição e Detalhes das Implementações - TAOD e YOLO.docx" deste projeto, estão os detalhes de implementação dos frameworks. Estão também a descrição dos scripts de instalação e inferência de cada framework.

No arquivo "Link Para Os Arquivos do Projeto.txt" deste projeto, está o link para todos os arquivos do projeto necessários para reproduzir o ambiente de testes e inferência. Contém os arquivos do dataset, scripts e os notebooks (google colab).

# Hiperparametros do Otimizador e âncoras

![image](https://github.com/mjf2004/projeto-mestrado/assets/71648038/5b8604e3-e624-4e6b-8a78-8d7090465240)



# Resultados
Experimentos Usando uma Base 80-20, treinados com 1.098 do total de 1.372 imagens.

![image](https://github.com/mjf2004/projeto-mestrado/assets/71648038/57687af7-528f-4861-b48c-2e9dd554ae5d)







