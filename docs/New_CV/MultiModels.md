modalities:  see objects, hear sounds, feel texture, smell odors, read text and so on. Modality is way in which something happens. Multiple sub concepts one should be familiar with:
- **Representation:** computer interpretable descriptions of heterogeneous data from multiple modalities.
- **translation:** represents process of changing data from one modality to another.
- **alignment:** identifying relations between elements from one or more modalities.
- **fusion:** process of joining information from 2 or more modalities to perform prediction task.
- **co-learning**: goal of transfering knowledge between modalities and their representations.

### Architecture
In general, multimodal architectures consist of three parts:

1. Unimodal encoders encode individual modalities. Usually, one for each input modality.
2. A fusion network that combines the features extracted from each input modality, during the encoding phase.
3. A classifier that accepts the fused data and makes predictions.

![](../Pasted%20image%2020230731002912.png)

from [here](https://blog.roboflow.com/multimodal-models/)

Encoder:
Encoder extracts features from input data. Different inputs can be passed to different Encoders.  These Encoders comprised of NNs with Non-linear transformations to extract increasingly abstract features from the input data. The outputs from these independent encoders are combined into a single vector.

Fusion:
combining information from different modalities into a single representation.

Usecases of dealing with just 2 modalities:

- Retrieval (image <> text) 
- Captioning (image -> text) 
- Generation (text -> image) 
- Visual question answering (image+text -> text) 
- Multimodal classification (image+text -> label) 
	- Better understanding/generation (image+text -> label/text)

Some popular models:
- [PaLI](https://sites.research.google/pali/?ref=blog.roboflow.com) (Pathways Language and Image model)
- [DALL-E](https://openai.com/product/dall-e-2?ref=blog.roboflow.com)
-  [Stable Diffusion](https://github.com/CompVis/stable-diffusion?ref=blog.roboflow.com).

**key innovations:**
Dall-e
- The use of a discrete latent space, which allows the model to learn a more structured and controllable representation of the generated images. 
- The model is optimized using a variant of the VAE loss function called the Gumbel-Softmax trick.
Stable Diffusion:
- Stable Diffusion uses a diffusion process, which involves iteratively adding noise to an initial image and then progressively removing the noise. By controlling the level of noise and the number of iterations, Stable Diffusion can generate diverse and high-quality images that match the input text prompt.
- Diffusion uses a contrastive loss function to encourage the generated images to be diverse and distinct from each other.
BEIT:
- The current state-of-the-art on the NLVR task is reached by [BEiT-3](https://arxiv.org/abs/2208.10442?ref=blog.roboflow.com). It is a transformer-based model that has been pre-trained on large-scale datasets of natural images and texts, such as ImageNet and Conceptual Captions.


## From the Book [here](https://slds-lmu.github.io/seminar_multimodal_dl/introduction.html)

##### Chapter-1
Outline:

- NLP:
	- Word embeddings
	- Attention
	- Self-attention
	- Bert
	- Transformers
- CV:
	- Resnet
	- Efficientnet
	- simCLR
	- BYOL
- Multimodal base concept models:
	- GANs
	- VAE
	- Dall-E
	- Glide
	- CLIP, ALIGN, Florence(these belong one group)
	- Flamingo

#### Chapter-2.1 NLP
2 major challenges were solved in NLP. 
- Word Embeddings are designed such a way that they capture the internal representations of words as dense vectors. so words with similar meaning will have similar embeddings.
- Another challenge is to map different lengths input and output data points using Encoders-Decoders(seq-seq)
- Another is Attention mechanism that help model to concentrate at particular parts in sentence. the Skip connections in transformer to avoid vanishing gradients & parallel processing unlike serial processing in RNNs. Also use of layer normalization(Layer normalization is a method of normalizing the activations of a layer before passing them to the next layer) to avoid vanishing gradients.  
- simple framework of contrastive learning from visual representations, which is called SimCLR, outperforms previous work on CNNs.
- Recent contrastive methods are trained by reducing the distance between representations of different augmented views of the same image (‘positive pairs’) and increasing the distance between representations of augmented views from different images (‘negative pairs’) is Bootstrap Your Own Latent (BYOL)
- Result of Advance architectures from NLP and CV gave rise to DAll-E. 

Embedding:
- An embedding is hereby defined as a vector of floating point values(with the length of the vector being a hyperparameter). 
- The values for the embedding are trainable parameters which are learned similarly to a model learning the weights for a dense layer.
![](../Pasted%20image%2020230731122527.png)
and for translation as well, words in other language also follow similar geometrical arrangements in space. here the languages are close.
![](../Pasted%20image%2020230731122617.png)
For example, the accuracy for translations between English and Vietnamese seemed significantly lower. This can be ascribed to both languages not having a good one-to-one correspondence because the concept of a word is different than in English. 

### BERT:
Only Encoder model. [MASK] token is used. Bi-Directional since context is important to get current word i.e MASKED.

### GPT-3:
Only Decoder model, Auto regressively predicts next word. 

### T5:
always a seq-seq model. Uses both Encoder and Decoder. Decoder is still a language model to predict next/upcoming word i.e Unidirectional. Encoder is a Masked LM to predict the part of input sequence (or) Masked word i.e Bidirectional. 

Using More data increased Complexity and Model sizes to Billion Parameters and size to GBs and TBs. Use of fine Tuning Techniques after Pre-training like Supervised Finetuning and RHLF.

### Chapter-2.2 CV
after alexnet, more CNN layers are added to add depth. So Resnets came up. Later increasing CNN layers width proved to be best approach. finally Increasing Image resolution, & Possibility of Scaling all 3 dimensions of Images led to EfficientNet. 
**Efficient NET**:
![](../Pasted%20image%2020230731131637.png)

**RESNET:**
for Vanishing gradients in Resnets, issue resoled by Normalized(kaiming HE) intialization, and Intermediate layer normalizations. 

Another obstacle was a degradation problem. It occurs when the network depth increases, followed by saturating and then rapidly decreasing accuracy. 

Residual learning is adopted to every few stacked layers where a building block is defined:

								y=F(x,{Wi})+x   (2.1)

x and y present the input and output vectors of the layers. Figure below visualizes the building block.

![Building block of residual learning (He et al. 2015).](https://slds-lmu.github.io/seminar_multimodal_dl/figures/01-chapter1/resnetBlock.png)

The function F(x,{Wi}) represents the residual mapping that is to be learned.

Leaderboard Table:

|Model|top-1 acc.|top-5 acc.|
|---|---|---|
|EfficientNet-B0 / ResNet-50|77.1 / 76|93.3 / 93|
|EfficientNet-B1 / ResNet-152|79.1 / 77.8|94.4 / 93.8|
|EfficientNet-B2|80.1|94.9|
|EfficientNet-B3 / ResNeXt-101|81.6 / 80.9|95.7 / 95.6|
|EfficientNet-B4|82.9|96.4|
|EfficientNet-B5|83.6|96.7|
|EfficientNet-B6|84|96.8|
|EfficientNet-B7 / GPipe|**84.3** / 84.3|**97** / 97|

**VIT**:
![](../Pasted%20image%2020230731133416.png)
image is is reshaped into a sequence of flattened 2-dimensional patches. usually 16×16 and map them to D dimensions with a trainable linear projection to create patch embeddings.


### 2.3 Contrastive Learning:
Process of labelling large unlabelled datasets is time-consuming and expensive. researchers assumed it could be solved with Contrastive learning framework. 

**SimCLR**: idea is to have 2 copies of same image, to train 2 networks and compared. 
problem: is that it dobules the size of dataset, and became expensive and infeasible. 

**BYOL**: Bootstrap your own latent is introduced to avoid doubling dataset size like SimCLR. Idea is to bootstrap its own representations of same image.

#### CHAPTER-3




References:

- https://blog.roboflow.com/multimodal-models/

- https://web.stanford.edu/class/cs224n/slides/Multimodal-Deep-Learning-CS224n-Kiela.pdf

- https://slds-lmu.github.io/seminar_multimodal_dl/index.html

