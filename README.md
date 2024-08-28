# Multilingual Complex Named Entity Recognition

## Project Description

This project is part of the In-Context Learning (ICL) course at the University of Cologne. The focus of this project is to experiment with and compare the performance of the [**LLaMA 3.1**](https://llama.meta.com/) and **Microsoft Phi** models on the [**SemEval 2022 Task 11: MultiCoNER Multilingual Complex Named Entity Recognition**](https://multiconer.github.io/multiconer_1/).

### Task Overview

The goal of the [SemEval 2022 Task 11](https://multiconer.github.io/multiconer_1/) is to develop Named Entity Recognition (NER) systems that can identify complex and semantically ambiguous entities in short, low-context texts across 11 languages. The challenge includes:

- Developing NER models for any or all of the 11 languages.
- Evaluating the models on provided test datasets, which include additional domain adaptation challenges like questions and short search queries.

## Requirements

To run this project, you need the following:

- Python 3.10 or higher
- Jupyter Notebook
- Required Python libraries listed in `requirements.txt`
- Access to the LLaMA 3.1 and Microsoft Phi models (instructions provided below)

## Getting Started

### 1. Clone the Repository and Set Up the Environment

1. Clone the repository and navigate to the project directory:

    ```bash
    git clone https://github.com/S0PEX/ICL-MultiCoNER.git
    cd ICL-MultiCoNER
    ```

2. Create a virtual environment and activate it:

    - On macOS/Linux:

      ```bash
      python3 -m venv venv
      source venv/bin/activate
      ```

    - On Windows:

      ```bash
      python -m venv venv
      venv\Scripts\activate
      ```

3. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

### 2. Download the Models

- **LLaMA 3.1**: Follow the instructions provided [here](#) to download and set up the LLaMA 3.1 model.
- **Microsoft Phi**: Follow the instructions provided [here](#) to download and set up the Microsoft Phi model.

### 3. Prepare the Data

The dataset for this project is hosted on AWS. To download the data, you will need to use the AWS CLI. Follow these steps:

1. **Install AWS CLI**: If you haven't already installed the AWS CLI, you can do so by following the installation instructions on the [AWS CLI documentation](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html).

2. **Download the Data**:

    First, navigate to the `data/` directory in your local project folder:

    ```bash
    cd data/
    ```

    Run the following command to list the available files:

    ```bash
    aws s3 ls --no-sign-request s3://multiconer/multiconer2022/
    ```

    To download the data, use the following command (from inside the `data/` folder):

    ```bash
    aws s3 sync s3://multiconer/multiconer2022/ multiconer2022/ --no-sign-request
    ```

    This command will sync the contents of the S3 bucket to a subdirectory named `multiconer2022/` within the `data/` directory in your local project folder.

3. **Verify the Download**:

    Ensure that the data has been successfully downloaded by checking the contents of the `data/multiconer2022/` directory.

### 4. Run Jupyter Notebooks

All experiments are conducted in Jupyter Notebooks. To start the notebook environment, run:

```bash
jupyter notebook
```
Open and execute the notebooks in the `notebooks/` directory to conduct experiments and analyze the results.

## Project Structure
```bash
ICL-MultiCoNER/
│
├── data/                   # Dataset files
├── models/                 # Model files and checkpoints
├── scripts/                # Scripts for data processing and model training
├── notebooks/              # Jupyter notebooks for analysis and experimentation
├── requirements.txt        # Python dependencies
```

## License

This project is licensed under the MIT License. All third-party code and libraries used in this project are licensed under their respective licenses. Please refer to the individual libraries for more details.