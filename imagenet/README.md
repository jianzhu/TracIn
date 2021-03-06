# ImageNet
The notebooks are meant to be read to gain insights and adapted to your dataset. Running the notebooks require work such as preparing ImageNet data and checkpoints during training. To read the notebook, it is easier to read from colab by clicking the **Open In Colab** badge due to file size.   

## If you really want to run the colab/notebook
* The notebook is prepared with Colab + TPU. To convert it for GPUs, please replace TPU strategy with GPU strategy. For details, please refer to [tf.distribute.Strategy](https://www.tensorflow.org/api_docs/python/tf/distribute/Strategy).
* Running with Colab can be easier since it provides free TPU quota.
* Download [ImageNet](http://www.image-net.org/) and load with [TensorFlow Datasets](https://www.tensorflow.org/datasets). Please refer to [tfds imagenet2012](https://www.tensorflow.org/datasets/catalog/imagenet2012) for instructions. In the notebooks, we iterate tfds for calculation and visualize by reading raw data. 
* [Train ResNet-50](https://github.com/frederick0329/TrackIn/blob/master/imagenet/resnet50/trainer.py) and save the [checkpoints](https://www.tensorflow.org/guide/checkpoint) of each epoch. 

## Application of TrackIn
* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/frederick0329/TrackIn/blob/master/imagenet/resnet50_imagenet_self_influence.ipynb) Inspecting Training data with Self-Influence
* [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/frederick0329/TrackIn/blob/master/imagenet/resnet50_imagenet_proponents_opponents.ipynb) Identifying Influential Training Points (Proponents and Opponents) of a Test point 
  * Cosider replacing the brute-force nearest neighbor with [ScaNN](https://github.com/google-research/google-research/tree/master/scann) to run on full ImageNet instead of 10%. 
