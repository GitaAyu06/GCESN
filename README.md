# Graph Convolutional Echo State Network (GCESN)
We proposed a reservoir-based graph convolution network called GCESN (Graph Convolution Echo State Network), which updates node embeddings by performing graph convolution iteratively using fixed, randomly initialized reservoir weights. A single GCESN layer can perform graph convolution to integrate information from neighbouring nodes that are up to k-hops away by iterating the process up to k times. Additionally, the leaky integrator in the reservoir is designed to control the oversmoothing effect by preserving the initial node embedding during node aggregation.

GCESN has three 

![gcesn](images/gcesn-1layer.png)

## GCESN Implementation for Graph Classification
![classification](images/gcesn-classification.png)

## GCESN Implementation for Graph Generation 
![generation](images/gcesn-generation.png)

### Dependency
To run the

###