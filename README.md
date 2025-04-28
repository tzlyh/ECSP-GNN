## Project Overview
The CAAH - GNN project aims to find the optimal radius value for specific biological sequence analysis tasks through a series of algorithms and function calculations, and evaluate the accuracy (ACC) of the results and other relevant indicators. This project can be applied in the field of bioinformatics, such as protein structure analysis and drug development, which helps to gain a deeper understanding of the active characteristics of biological sequences.

## Environment Installation
This project relies on a specific environment configuration. You can use the `CAAH - GNN.yaml` file to create the required environment. Please ensure that you have installed Anaconda or Miniconda. The following are the specific installation steps:

1. Clone the project repository to your local machine:
```bash
git clone <Project Repository URL>
cd <Project Directory>
```

2. Create a virtual environment using the `CAAH - GNN.yaml` file:
```bash
conda env create -f CAAH - GNN.yaml
```

3. Activate the newly created virtual environment:
```bash
conda activate <Environment Name>  # The environment name is defined in the CAAH - GNN.yaml file
```

## Running the Project
After completing the environment installation, you can directly execute the `main.py` script to obtain the final results in one step, including the optimal radius value, ACC, and other evaluation indicators.
```bash
python main.py
```

## Core Functions and Implementation Steps
### 1. Calculate the Maximum Distance (MaxDistance)
Obtain `MaxDistance` through the `findMaxDistance` function. `MaxDistance` refers to the distance from the active center of all sequences to the farthest amino group, and the smallest value is selected from these distances.

### 2. Equidistant Layered Sampling (EquidistantLayeredSampling)
Use the `EquidistantLayeredSampling` function to calculate different ACC values corresponding to radii in the range of `[4Å, 8Å, 12Å, ... , MaxDistance]` (increasing by 4Å each time), and find the smallest radius `R0` when the maximum ACC is achieved.

### 3. Calculate the Parameter k (caculateK)
Calculate the following parameters through the `caculateK` function:
- `R1`: The maximum radius value corresponding to the second - largest ACC in the range of `[4Å~R0)`.
- `R2`: The minimum radius value corresponding to the second - largest ACC in the range of `(R0~MaxDistance]`.
- `k1 = R1/R0`: The initial value of `cansu`.
- `k2 = R2/R0`: The upper limit value of `cansu`. When `cansu = k2`, no further learning will be carried out.

### 4. Micro - scale Adaptive Sampling (Micro_scaleAdaptiveSampling)
Utilize the `Micro_scaleAdaptiveSampling` function for adaptive learning to finally obtain the optimal radius value, ACC, and other evaluation indicators.

## Example Explanation
Suppose we have a set of sample biological sequence data. Place it in the specified input directory of the project. After executing the `main.py` script, the program will automatically perform calculations according to the above steps. Finally, the optimal radius value, ACC, and other evaluation indicators will be output in the console, and corresponding result files may also be generated and saved to the specified output directory.

## Version Information
- Current Version: v1.0
- Release Date: [Specific Date]

## Update Log
### v1.0
- The initial version is released, implementing core calculation functions, including the `findMaxDistance`, `EquidistantLayeredSampling`, `caculateK`, and `Micro_scaleAdaptiveSampling` functions.
- An environment configuration file `CAAH - GNN.yaml` is provided to facilitate users to install the dependent environment.

Please replace `<Project Repository URL>`, `<Project Directory>`, `<Environment Name>`, and `[Specific Date]` with the actual information. This README content should better help users understand and use your project. 
