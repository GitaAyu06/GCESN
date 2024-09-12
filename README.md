# Graph Convolutional Echo State Network (GCESN)
We proposed a reservoir-based graph convolution network, which updates node embeddings by performing graph convolution iteratively using fixed, randomly initialized reservoir weights. A single GCESN layer can perform graph convolution to integrate information from neighbouring nodes that are up to k-hops away by iterating the process up to k times. Additionally, the leaky integrator in the reservoir is designed to control the oversmoothing effect by preserving the initial node embedding during node aggregation.

GCESN consits of three components, which are the input layer, the graph convolution reservoir layer, the and the linear output layer.

![gcesn](images/gcesn-1layer.png)

### GCESN Implementation for Graph Classification
GCESN implementation in a graph classification model is illustrated in the figure below:
![classification](images/gcesn_classification_compressed.png)

### GCESN Implementation for Graph Generation 
GCESN implementation in a graph transformer model for brain evolution prediction is illustrated in the figure below:
![generation](images/gcesn_generation_compressed.png)

## Source Code
#### Installation
GCESN was developed using Python version 3.10.12 with CUDA toolkit v12.0. All library that is used for running GCESN codes are available in [requirements](requirements.txt). Before running all codes in this repository, installed all the required libraries by running the following command on terminal

```
pip install -r requirements.txt
```

### File structure
| File | Description |
| ------ | ------ |
| models/ | folder contains all stored model throughout all experiments |
| graph-preprocessing.ipynb | code to preprocess the graph dataset |
| graph-eda.ipynb | code to do exploratory data analysis on the graph dataset|
| experiments-classification_num_layers.ipynb | code to do experiments on graph classification using with varying number of GCESN layers |
| experiments-classification_reservoir_params.ipynb | code to do experiments on graph classification using with varying GCESN reservoir parameters |
| experiments-generation_benchmark_models.ipynb | code to do experiments on brain graph evolution prediction using benchmark models (Identity function, RBGM, EvoGraphNet)|
| experiments-generation_transformers_models.ipynb | code to do experiments on brain graph evolution prediction using proposed graph transformer models|
| experiments-node_features_init.ipynb | code for running simple experiments on different node feature initialization method|

### Input Data
All graph data used as input for the codes in this repository must include an adjacency matrix and a node feature matrix, both in NumPy array format. The required shapes are as follows:format with the following shape:
- The adjacency matrix shape: (n_samples, n_timepoints, n_nodes, n_nodes) 
- The node feature matrix shape: (n_samples, n_timepoints, n_nodes, feature_dim)
