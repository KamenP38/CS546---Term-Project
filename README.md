# Benchmarking Pandas with various optimizations

With the growing size of datasets and increasing demand for efficient computation, identifying the right tools for specific workloads has become essential. This project benchmarks Pandas against high-performance libraries like cuDF, Polars, and Ray, offering insights into their strengths and weaknesses to help data scientists and engineers make informed decisions.

The dataset used for this project is Thesios by Google, a collection of I/O traces capturing detailed file system interactions and storage performance metrics, ideal for benchmarking storage systems and data processing frameworks.

## Description of evaluation files

Each evaluation file contains implementations of queries of various complexities with different libraries/frameworks. The researcher needs to install the necessary libraries in order to continue working without issues.

Each evaluation can be done by calling the necessary function, just like in the example given within each file. The user must change the location of the file they are going to be testing on (e. g., dataset-1.csv), as well as the file in which they want to store the logged data regarding the memory usage and execution time (e. g., dataset-1-results.txt).

Here is an example:
- base_simple_pandas_queries("datasets_thesios_io_traces/dataset-200k.csv", "results_simple_queries_csv/results_pandas_plain_simple_200k.txt")

## Requirements for working with the libraries

1. Create and activate a virtual environment. Using a virtual environment prevents package conflicts with other projects.
   
- Create a virtual environment:
python -m venv env

- Activate the virtual environment:
source env/bin/activate


2. Install the Requirements
   
Use pip to install all libraries from the requirements.txt file.
pip install -r requirements.txt

NOTES:
- GPU Libraries
If you intend to use cudf, dask-cudf, and rmm, ensure that a compatible version of CUDA is installed on your system. Check the official documentation for compatibility.
- Ray
If installing on macOS/Linux, additional setup for Ray may be required (e.g., installing ray[default] or setting up environment variables).


> **Note**
> All experiments were conducted on a single ASUS laptop equipped with an Intel Core i7-12700H 12th Gen CPU, featuring 14 cores and 20 logical processors, thereby enabling robust multi-core processing capabilities. The system utilized 10 GB of available RAM and was powered by an NVIDIA GeForce RTX 4060 GPU with 8 GB of GPU memory, providing substantial memory bandwidth and parallel processing power essential for evaluating GPU-accelerated frameworks like cuDF. Additionally, the machine operated on Windows Subsystem for Linux (WSL) with Ubuntu 24.04.1 LTS.