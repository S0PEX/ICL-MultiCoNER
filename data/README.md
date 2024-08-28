# Data Preparation Instructions

This directory contains the dataset for the [**Multilingual Complex Named Entity Recognition (MultiCoNER)**](https://multiconer.github.io/multiconer_1/) project. The data is hosted on AWS and needs to be downloaded using the AWS CLI.

## Downloading the Data

To download the dataset, follow these steps:

1. **Install AWS CLI**: If you haven't already installed the AWS CLI, you can do so by following the installation instructions on the [AWS CLI documentation](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html).

2. **Download the Data**:

    First, navigate to this `data/` directory:

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

    This command will sync the contents of the S3 bucket to a subdirectory named `multiconer2022/` within this `data/` directory.

3. **Verify the Download**:

    Ensure that the data has been successfully downloaded by checking the contents of the `data/multiconer2022/` directory.

If you encounter any issues or need further assistance, please refer to the [AWS CLI documentation](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html) or contact support.
