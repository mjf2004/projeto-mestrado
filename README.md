# projeto-mestrado
Detecção de máscara com os algoritmos de detecção Faster-RCNN, SSD e YOLO. O projeto de mestrado iniciado em 2020 e concluído em 2023.

Projeto de mestrado iniciado em 2000. Neste projeto foram usados nove modelos pré-treinados de redes neurais e três algoritmos de detecção de objetos Faster R-CNN, SSD e YOLO.

# Recursos:
Frameworks utilizados: Tensorflow API Object Detection e Darknet.

O hardware considerado para todos os experimentos, tanto para o treinamento e avaliação, quanto para a inferência são as seguintes: 2 Processadores Intel(R) Xeon(R) CPU @ 2.20GHz, 25 GB de memória RAM e placa de vídeo Tesla P100-PCIE; informações retiradas no terminal do Google Colaboratory.

O _dataset_, _scripts_ e os notebooks (google colab) estão disponíveis no google drive, no link: bit.ly/3CS0FfZ

# Detalhes da implementação.

#Tensorflow API Object Detection.

Estrutura de diretórios:

Um diretório raiz chamado “tensorflow” e dois subdiretórios “scripts” e  “workspace”. No diretório “scripts” temos um subdiretório “preprocessing”, que contém o script generate_tfrecord.py para geração dos arquivos train.record e test.record, Os scripts estão em bit.ly/3CS0FfZ.

O diretório “workspace” contém um subdiretório nomeado como “trained_demo”.  No diretório “trained_demo” temos os subdiretórios “annotations”, “exported-models”, “images”, “models” e “pre-trained-models”, o papel de cada um deles são descritos da seguinte maneira:

•	Annotations – Contém um arquivo label_map.pbtxt (arquivo criado em branco com o aplicativo Notepad++), que contém o nome das categorias. No mesmo local, ainda se encontra os arquivos train.record e test.record;

•	Exported-models – Local onde será salvo o modelo para inferência;

•	Images – Contém subdiretórios “train” e “test”, respectivamente as imagens de treino e as imagens de teste;

•	Models – local onde armazenam os pesos treinados com o arquivo de índice “ckpt-1.index”, “ckpt-2.index” e assim por diante. Nesse local, temos um arquivo de checkpoint (usado para continuar o treinamento de um ponto de parada) e um arquivo de configuração pipeline.config, onde os parâmetros alterados foram:

a)	num_classes: número de classes a ser detectado;

b)	batch_size: tamanho do lote;

c)	fine_tune_checkpoint: local dos pesos pré-treinado;

d)	fine_tune_checkpoint_type: “detection”;

e)	use_bfloat16: false;

f)	label_map_path: local do arquivo label_map.pbtxt;

g)	train_input_reader e input_path: local do arquivos train.record;

h)	metrics_set: Alterado para "pascal_voc_detection_metrics ";

i)	eval_input_reader e input_path: local do arquivo test.record;

j)	num_steps: total de iterações.

•	Pre-trained-models: contém o arquivo pipeline.config original e um subdiretório com o nome “checkpoint” com o download dos pesos do modelo pré-treinado baixado do repositório.

Treinamento, Exportação e Avaliação

Para facilitar a execução dos comandos de treinamento, exportação do modelo e avaliação, dois arquivos “model_main_tf2.py” (script de treinamento) e “exporter_main_v2.py” (script de exportação do modelo) foram copiados do diretório de instalação da Tensorflow API Object Detection para o diretório “trained_demo”. Considerando uma nova célula do terminal, no nível do diretório “trained_demo” usando os pesos da arquitetura SSD Resnet 50 v1 FPN, os comandos são mostrados na tabela abaixo:






