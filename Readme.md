# Flow Log Parser

## Overview
This program parses AWS-style flow log data to map each log entry to a tag based on a lookup table (`lookup_table.csv`). It supports multiple versions of flow logs (1, 2, 3, and 5) and outputs into:
1. A count of tags applied to flow log entries.
2. A count of unique port/protocol combinations.

## Features
- Handles versions 1, 2, 3, and 5 of flow logs.
- Maps destination port and protocol combinations to predefined tags.
- Outputs:
  - Count of matches for each tag.
  - Count of unique port/protocol combinations.

## Assumptions
1. **Default Log Format**: The program can take AWS flow log formats for versions 1, 2, 3, and 5. Custom formats are not supported.
2. **Supported Protocols**: Only TCP and UDP protocols are processed.
3. **Encoding**: The program assumes `lookup_table.csv` is encoded in `utf-8` or `utf-8-sig`.
4. **Mandatory Fields**: The program expects specific fields (e.g., `dstport`, `protocol`) to exist in the flow logs.

## File Structure
- `flow_log.txt`: Input file containing flow log data.
- `lookup_table.csv`: Lookup table mapping `dstport` and `protocol` combinations to tags.
- `output.txt`: Output file containing tag and port/protocol combination counts.
- `logFlow.ipynb`: The main program notebook.

## Installation and Setup
This program uses only the default Python standard library and requires no additional dependencies.

### Running the Notebook in Google Colab
1. **Upload the Notebook**:
   - Go to [Google Colab](https://colab.research.google.com/).
   - Upload `logFlow.ipynb` using the "File > Upload notebook" option.

2. **Upload Input Files**:
   - Once the notebook is open in Google Colab, use the file upload cell provided in the notebook to upload `logFlow.txt` and `lookup_table.csv`.
3. **Download the Output**:
   - After running all the cells, the `output.txt` file will be generated. Use the download link provided in the notebook to save the output to your local machine.