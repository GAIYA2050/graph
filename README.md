# graph
### 关于graph可做的方向
- 图的任务也有很大的不同，可以是node-focused问题，如节点分类和链接预测，也可以是graph-focused问题，如图分类和图生成。不同的结构和任务需要不同的模型架构来处理特定的问题。   
据此，现在要做的方向是视频描述，后边可以做一些图像生成的，graph与GAN结合的一些工作，但是似乎是有了。。再具体看看。
- 关于视频描述任务：有一篇Spatio-temporal graph convolutional networks: A deep learning framework for traffic forecasting,可以考虑进去，这个时域的问题;;;;;;;;另外关于关节点做行为识别的问题，也找来看看是不是时空-图卷积

### 近期Graph的学习任务 
- semantic role labeling 代码
- Hierarchical Graph Representation Learning with Differentiable Pooling [代码](https://github.com/RexYing/diffpool)
- Learning Conditioned Graph Structures for Interpretable Visual Question Answering 代码：github.com/aimbrain/vqa-project.
condition 是基于question.那么在视频描述中也可以基于监督学习本身带有的标签，在Inference时，则，直接利用训练好的graph参数（此处可以参考一下few-shot）
- 其他关于视觉问答的论文
- Graph Neural Networks: A Review of Methods and Applications提到了一些关于视觉问答的论文可以找出来，看一看，还有关于源代码的部分

### 待学习：
- 带边信息的图(Edge-informative Graph)
每条边都有信息，比如权值或边的类型。例如G2S和R-GCN。
1. **Graph-to-Sequence Learning using Gated Graph Neural Networks.**
*Daniel Beck, Gholamreza Haffari, Trevor Cohn.* ACL 2018. [paper](https://arxiv.org/pdf/1806.09835.pdf)
1. **Modeling Relational Data with Graph Convolutional Networks.**
*Michael Schlichtkrull, Thomas N. Kipf, Peter Bloem, Rianne van den Berg, Ivan Titov, Max Welling.* ESWC 2018. [paper](https://arxiv.org/pdf/1703.06103.pdf)

- 使用不同训练方法的图变体
1. **FastGCN: Fast Learning with Graph Convolutional Networks via Importance Sampling.**
*Jie Chen, Tengfei Ma, Cao Xiao.* ICLR 2018. [paper](https://arxiv.org/pdf/1801.10247.pdf) [[code]](https://github.com/matenure/FastGCN)



### 问题
在Graph Neural Networks: A Review of Methods and Applications论文P16中，也提到了语义角色标注这篇文章，说"special variant of the GCN "；
在语义角色标注的本文中，也提到了More formally....这一处需要再理解一些。


### 通过池化，提出了一种graph classification的方法</br>
[Hierarchical Graph Representation Learning with Differentiable Pooling](https://arxiv.org/pdf/1806.08804.pdf),[code](https://github.com/RexYing/diffpool)


## 总结性质的
### github上的某篇总结-介绍了相关的论文、博客、以及研究者</br>
https://github.com/sungyongs/graph-based-nn</br>
https://github.com/thunlp/GNNPapers</br>
[Spatio-temporal modeling 论文列表(主要是graph convolution相关)](https://github.com/Eilene/spatio-temporal-paper-list)
### 综述论文
- [Deep Learning on Graphs: A Survey](https://arxiv.org/abs/1812.04202)  
[[新智元解读]](https://mp.weixin.qq.com/s/eelcT5x_kWC0dDt0_Ph4qg)
- [Graph Neural Networks: A Review of Methods and Applications](https://arxiv.org/abs/1812.08434)  
[[新智元解读]](https://mp.weixin.qq.com/s/h4jQWJlQV2Ew3SpuF8k5Hw)
- [A Comprehensive Survey on Graph Neural Networks](https://arxiv.org/abs/1901.00596)
- [Relational inductive biases, deep learning, and graph networks](https://arxiv.org/pdf/1806.01261.pdf)

## 谱上的图卷积发展:spectral-based graph convolutional networks

- 以下四篇是按照时间轴，依次在前一篇的文章上进行改进的
1. [The Emerging Field of Signal Processing on Graphs](https://arxiv.org/pdf/1211.0053.pdf)
1. [Spectral Networks and Locally Connected Networks on Graphs](https://arxiv.org/abs/1312.6203)
1. [Convolutional Neural Networks on Graphs with Fast Localized Spectral Filtering](https://arxiv.org/abs/1606.09375), [[PyTorch Code]](https://github.com/xbresson/graph_convnets_pytorch/blob/master/README.md) [[TF Code]](https://github.com/mdeff/cnn_graph)
1. [Semi-Supervised Classification with Graph Convolutional Networks](https://arxiv.org/abs/1609.02907), [[Code]](https://github.com/tkipf/gcn), [[Blog]](http://tkipf.github.io/graph-convolutional-networks/)

- 以下三篇是在"A Comprehensive Survey on Graph Neural Networks"这篇综述中提到的另外三篇
1. [Deep convolutional networks on graph-structured data](https://arxiv.org/abs/1506.05163)
1. [Adaptive graph convolutional neural networks](https://arxiv.org/abs/1801.03226) (AAAI 2018) 可接受任意图结构和规模的图作为输入
1. [Cayleynets: Graph convolutional neural networks with complex rational spectral filters](https://arxiv.org/abs/1705.07664)

- 谱上的图卷积网络的缺陷：   
**spectral methods usually handle the whole graph simultaneously and are difficult to parallel or scale to large graphs**

## 空间上的图卷积：spatial-based graph convolutional networks( by "A Comprehensive Survey on Graph Neural Networks")

1. [Inductive representation learning on large graphs](http://papers.nips.cc/paper/6703-inductive-representation-learning-on-large-graphs.pdf)  (GraphSAGE)
1. [Geometric deep learning on graphs and manifolds using mixture model cnns](http://openaccess.thecvf.com/content_cvpr_2017/papers/Monti_Geometric_Deep_Learning_CVPR_2017_paper.pdf)
1. [Learning convolutional neural networks for graphs](http://proceedings.mlr.press/v48/niepert16.pdf)
1. [Large-scale learnable graph convolutional networks](https://dl.acm.org/citation.cfm?id=3219947)  (LGCN) 

- **Together with sampling strategies, the computation can be performed in a batch of nodes instead of the whole graph** (GraphSAGE and LGCN)

## 改善GCN在训练方面的缺陷: Training Methods
- **by "A Comprehensive Survey on Graph Neural Networks"**
- [1stChebNet(semi-supervised GCN)](https://arxiv.org/abs/1609.02907)：the main drawback of 1stChebNet is that the computation cost increases exponentially with the increase of the number of 1stChebNet layers during batch training. Each node in the last layer has to expand its neighborhood recursively across previous layers.
1. [Fastgcn: fast learning with graph convolutional networks via importance sampling (ICLR 2018)](https://arxiv.org/abs/1801.10247) 
assume the rescaled adjacent matrix A comes from a sampling distribution. 
1. [Stochastic training of graph convolutional networks with variance reduction (ICML 2018)](https://arxiv.org/abs/1710.10568) 
reduce the receptive field size of the graph convolution to an arbitrary small scale by sampling neighborhoods and using historical hidden representations.
1. [Adaptive sampling towards fast graph representation learning (NIPS 2018)](https://arxiv.org/abs/1809.05343) 
propose an adaptive layer-wise sampling approach to accelerate the training of 1stChebNet, where sampling for the lower layer is conditioned on the top one. 

- **by "Graph Neural Networks: A Review of Methods and Applications"**
- GCN requires the full graph Laplacian, which is computational-consuming for large graphs. Furthermore, The embedding of a node at layer L is computed recursively by the embeddings of all its neighbors at layer L − 1. Therefore, the receptive field of a single node grows exponentially with respect to the number of layers, so computing gradient for a single node costs a lot. Finally, GCN is trained
independently for a fixed graph, which lacks the ability for inductive learning.
1. [Inductive representation learning on large graphs (NIPS 2017)](https://arxiv.org/abs/1706.02216)
1. [Fastgcn: fast learning with graph convolutional networks via importance sampling (ICLR 2018)](https://arxiv.org/abs/1801.10247)  
directly samples the receptive field for each layer.
1. [Adaptive sampling towards fast graph representation learning (NIPS 2018)](https://arxiv.org/abs/1809.05343) 
 introduces a parameterized and trainable sampler to perform layerwise sampling conditioned on the former layer.
1. [Stochastic training of graph convolutional networks with variance reduction (ICML 2018)](https://arxiv.org/abs/1710.10568) 
proposed a control-variate based stochastic approximation algorithms for GCN by utilizing the historical activations of nodes as a control variate. 
1. [Deeper insights into graph convolutional networks for semi-supervised learning  (arXiv:1801.07606, 2018)](https://arxiv.org/abs/1801.07606)  


## input allow edge features 
- ( by "A Comprehensive Survey on Graph Neural Networks")
1. GNN (2009) The graph neural network model
1. MPNN (2017) Neural message passing for quantum chemistry
1. DCNN (2016) Diffusion-convolutional neural networks
1. PATCHY-SAN (2016) Learning convolutional neural networks for graphs

- ( by "Deep Learning on Graphs: A Survey")
1. Geniepath:Graph neural networks with adaptive receptive paths
1. Dual graph convolutional networks for graph-based semi-supervised classification
1. Signed graph convolutional network



## 图表达：Graph level representation/Readout Operations
**Order invariance**  A critical requirement for the graph readout operation is that the operation should be invariant to the order
of nodes, i.e. if we change the indices of nodes and edges using a bijective function between two vertex sets, representation of the whole graph should not change.   

**一. Statistics** ( by "Deep Learning on Graphs: A Survey")
- The most basic operations that are order invariant are simple statistics like taking **sum**, **average** or **max-pooling**
1. Convolutional networks on graphs for learning molecular fingerprints
1. Diffusion-convolutional neural networks
- other 
1. Molecular graph convolutions: moving beyond fingerprints
1. Spectral networks and locally connected networks on graphs

**二. Hierarchical clustering** ( by "Deep Learning on Graphs: A Survey")
1. Spectral networks and locally connected networks on graphs
1. Deep convolutional networks on graph-structured data
1. [Hierarchical Graph Representation Learning with Differentiable Pooling](https://arxiv.org/pdf/1806.08804.pdf) [[code]](https://github.com/RexYing/diffpool)

**三. Graph Pooling Modules** (by "A Comprehensive Survey on Graph Neural Networks")
1. Convolutional neural networks on graphs with fast localized spectral filtering (NIPS 2016)
1. Deep convolutional networks on graph-structured data
1. An end-to-end deep learning architecture for graph classification (AAAI 2018) [[code]](https://github.com/muhanzhang/DGCNN)  [[pytorch code]](https://github.com/muhanzhang/pytorch_DGCNN)
1. Hierarchical graph representation learning with differentiable pooling (NIPS 2018)

# GCN的应用

## 自然语言处理( by "Deep Learning on Graphs: A Survey")

### 语义角色标注
[Encoding Sentences with Graph Convolutional Networks for Semantic Role Labeling](https://arxiv.org/abs/1703.04826)</br>
* [[官方code(theano 0.8.2,lasagne 0.1)]](https://github.com/diegma/neural-dep-srl)  [[复现pytorch]](https://github.com/kervyRivas/Graph-convolutional)
* [专知讲解](https://mp.weixin.qq.com/s/c6ZhSk4r3pvnjHsvpwkkSw)
* by yaya:阅读该篇文章主要是来源于这篇将图卷积用于图像描述的文章:Exploring Visual Relationship for Image Captioning</br>
这两篇文章采用的图卷积公式都是一样的，但是我认为很奇怪，而且b是如何由edge获得的，将进一步阅读代码，稍后解释。</br>
<img src="https://github.com/ShiYaya/graph/blob/master/images/gcn%2Bformulation.png" width="200" height="100" ></br>

### Neural Machine Translation
1. **Graph Convolutional Encoders for Syntax-aware Neural Machine Translation.**
*Joost Bastings, Ivan Titov, Wilker Aziz, Diego Marcheggiani, Khalil Sima'an.* EMNLP 2017. [paper](https://arxiv.org/pdf/1704.04675)


### 视觉问答( by "Graph Neural Networks: A Review of Methods and Applications")
1. **A simple neural network module for relational reasoning.**
*Adam Santoro, David Raposo, David G.T. Barrett, Mateusz Malinowski, Razvan Pascanu, Peter Battaglia, Timothy Lillicrap.* NIPS 2017. [paper](https://arxiv.org/pdf/1706.01427.pdf)
1. **Graph-Structured Representations for Visual Question Answering.**
*Damien Teney, Lingqiao Liu, Anton van den Hengel.* CVPR 2017. [paper](https://arxiv.org/pdf/1609.05600.pdf)
1. **Out of the Box: Reasoning with Graph Convolution Nets for Factual Visual Question Answering.**
*Medhini Narasimhan, Svetlana Lazebnik, Alexander Schwing.* NeurIPS 2018. [paper](http://papers.nips.cc/paper/7531-out-of-the-box-reasoning-with-graph-convolution-nets-for-factual-visual-question-answering.pdf)
1. **Learning Conditioned Graph Structures for Interpretable Visual Question Answering.**
*Will Norcliffe-Brown, Efstathios Vafeias, Sarah Parisot.* NeurIPS 2018. [paper](https://arxiv.org/pdf/1806.07243)  [[code]](https://github.com/aimbrain/vqa-project)
