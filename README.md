# Volcano Plot Generator

This Python program generates **volcano plots** from gene expression data, specifically from differential expression analysis results in `.xls` or `.xlsx` formats. The plots provide a visual representation of log2 fold-change values and p-values, helping identify significantly upregulated or downregulated genes.

![Example Usage Animation](https://github.com/dennisforster/volcano_plot_generator/blob/main/examples/usage.gif)

## Features

-   Reads data from `.xls` or `.xlsx` files.
-   Automatically categorizes genes as upregulated, downregulated, or neutral based on log2 fold-change and adjusted p-value thresholds.
-   Creates an interactive volcano plot (using Plotly) as an HTML file for easy sharing and visualization.
-   Creates a copy of `.xls` data in `.xlsx` format.

## Usage

1. Edit the `config.ini` file to adjust to your use case.
2. Run either the `volcano_plot.exe` or execute the Jupyter Notebook `volcano_plot.ipynb`

### Configuration

The script uses a configuration file (`config.ini`) to specify the following parameters:

-   `DATA_FOLDER`: Path to the folder containing the Excel files.
-   `LOG2FOLDCHANGE_COLUMN`: Name of the column representing the log2 fold-change values.
-   `PADJ_COLUMN`: Name of the column representing the adjusted p-values.
-   `GENENAME_COLUMN`: Name of the column representing the gene names.
-   `PVALUE_THRESHOLD`: Threshold for adjusted p-values to identify significant genes.
-   `LOG2FOLDCHANGE_THRESHOLD`: Threshold for log2-fold-change to classify genes as upregulated or downregulated.

Update these values in the `config.ini` file before running the script.

### Option 1: Running the Pre-Compiled `volcano_plot.exe`

If you don’t have Python installed, you can still run this tool by using the pre-compiled executable file. Check out the [Release page](https://github.com/dennisforster/volcano_plot_generator/releases/tag/v1.0.0) on the right-hand side of this page and follow the instructions:

1. **Download the executable** from the repository (`volcano_plot.exe`).
2. **Place your data file** in the same directory as the executable, or provide the path to the file in the configuration file (`config.ini`).
3. **Adjust settings in `config.ini`**, especially making sure that the file path and column names are set up correctly.
4. **Run the executable** by double-clicking the `.exe` file.
5. **An HTML file with the interactive volcano plot will be saved** in the same directory as the input file.
   You can now investigate the data by zooming into specific regions (click-and-drag to select a region, double-click to reset the view).

### Option 2: Running the Jupyter Notebook `volcano_plot.ipynb`

#### Requirements

To set up the required environment, use the `environment.yml` file provided in the repository. This file lists all necessary dependencies, so you don’t need to install packages individually:

1. **Install** [Anaconda](https://www.anaconda.com/products/distribution) or [Miniconda](https://docs.conda.io/en/latest/miniconda.html) if you haven't already.
2. **Create the environment** from the `environment.yml` file:

    ```bash
    conda env create -f environment.yml
    ```

3. **Activate the environment**:

    ```bash
    conda activate volcano-plot
    ```

Now you’re ready to use the tool in the configured environment.

#### Notebook Functions

The primary function in this script is `create_volcano_plot`, which generates a volcano plot for a given Excel file and parameters such as the required column names and thresholds.
Running the complete script will read all parameters from the `config.ini` and then execute this function on all Excel files in the specified data folder.
The generated volcano plot is saved as an HTML file in the same data folder.

## Disclaimer

This tool is provided for informational and educational purposes only. **The author is not responsible for any errors, inaccuracies, or misuse of this software.** If used in research or any professional setting, users are solely responsible for verifying the results and ensuring compliance with all relevant guidelines and standards. This software is provided "as is" without warranty of any kind. Use at your own discretion and risk.

## Contact Information

If you have any questions, suggestions or need further clarification, please feel free to reach out:

**Name:** [Prof. Dr. Dennis Forster](https://www.frankfurt-university.de/index.php?id=11587)  
**Email:** dennis.forster@fb3.fra-uas.de

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
