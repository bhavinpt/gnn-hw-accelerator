# GNN Hardware Accelerator
 This is my master's project. Currently, I am working on using FPGA to accelerate GNN computing and achieve speedup over CPU and GPUs. This is a year-long project and is planned to be completed by the end of 2023. 

GNN is a type of neural network designed to handle data structured as graphs, like social networks or molecule connections. GNNs process information from neighboring nodes and edges to understand relationships, making them useful for tasks like social network analysis and recommendation systems. They've gained attention for their ability to capture complex patterns within graph data.

![image](https://github.com/bhavinpt/gnn-hw-accelerator/assets/117598876/760a7a76-f1d5-48f4-a23b-efbaf6fea78e)

They operate on the principle of information aggregation and propagation within the graph's nodes and edges. 

### Here's a simplified explanation of how GNNs work

- Initialization: Nodes in the graph start with initial feature vectors.
- Aggregation: Nodes gather info from neighbors, combining their features.
- Update: Nodes use aggregated information to refine their feature vectors.
- Iteration: Steps 2 and 3 are repeated.
- Output: GNN produces predictions based on updated node features.

### Key concepts and techniques often used in GNNs include

- Convolutional Layers: Used to aggregate and update information, similar to how convolutional layers work in image processing.
- Aggregation Functions: Functions such as sum, and mean, are used to combine information from neighboring nodes.
- Message Passing: The process of aggregating and updating information through the graph is often called "message passing."
- Graph Pooling: In some cases, GNNs may incorporate graph pooling layers to downsample the graph and capture higher-level structural information.

![image](https://github.com/bhavinpt/gnn-hw-accelerator/assets/117598876/ac02edf6-69ff-4331-9556-884dd2fcf256)
![image](https://github.com/bhavinpt/gnn-hw-accelerator/assets/117598876/ad5cc82a-9257-4587-b1b0-26a82c4064c3)

_Source: Microsoft Research (https://www.microsoft.com/en-us/research/video/msr-cambridge-lecture-series-an-introduction-to-graph-neural-networks-models-and-applications)_


### Literature Review
Identified and studied some of the most popular GNN accelerators, some of the most relevant ones are listed below.
After studying these research papers, I have finalized the architecture of my accelerator, and I am currently working towards implementing it on FPGA using HLS. 

[FCCM 2020] EnGN: A High-Throughput and Energy-Efficient Accelerator for Large Graph Neural Networks.

T. Geng et al.S. T. Geng et al.S. [[Paper]](https://arxiv.org/pdf/2201.08475)

[FCCM 2022] GenGNN: A Generic FPGA Framework for Graph Neural Network Acceleration.

Abi-Karam S, He Y, Sarkar R, et al. [[Paper]](https://arxiv.org/pdf/2201.08475) [[GitHub]](https://github.com/sharc-lab/gengnn)

[FCCM 2021] BoostGCN: A Framework for Optimizing GCN Inference on FPGA.

Zhang B, Kannan R, Prasanna V. [[Paper]](https://ieeexplore.ieee.org/abstract/document/9444065)

[arXiv 2021] LW-GCN: A Lightweight FPGA-based Graph Convolutional Network Accelerator.

Tao Z, Wu C, Liang Y, et al. [[Paper]](https://arxiv.org/abs/2111.03184)

### Below is the current progress on implementation

- Completed software implementation and obtained binaries and golden outputs: https://colab.research.google.com/drive/1DY1Cy63_rn5fM8O3b4EBGhJ6Yd6NfZDD?usp=drive_link
- Working on Block MatMul with loop unrolling and pipeline
- Check resources and performance for different block sizes, and pick the best
- Implement MatMul with Vitis BLAS library: https://xilinx.github.io/Vitis_Libraries/blas/2020.1/user_guide/L3/L3_example_gemm.html
- Analyze resource, performance, and parameter tuning.
- Compare both, and pick the best. 
- Use the best model parameters.
- Verify the results
- Again compare resources and performance for both
- Try reduced precision
- Compare performance

The goal is to achieve speedup over GPU & CPU on the below graph datasets.

1. Cora
2. PubMed
3. Reddit

Code will be available soon on this repo. :)
