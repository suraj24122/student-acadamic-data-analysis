JSON to Excel Converter
This repository contains a simple Python script to convert student data from a JSON file into an Excel spreadsheet.

Table of Contents
Features

Files in this Repository

Prerequisites

Usage

Project Structure

Contributing

License

Features
JSON Data Loading: Loads student data from a specified JSON file.

Excel Conversion: Converts the loaded JSON data into a structured Excel spreadsheet (.xlsx format).

Pandas Integration: Utilizes the pandas library for efficient data manipulation and Excel export.

Files in this Repository
Task_1.ipynb: A Jupyter Notebook containing the Python code for loading JSON data and converting it to an Excel file.

Students_data.json: A sample JSON file containing student records used as input for the conversion script.

Students_data_output.xlsx (Generated): The output Excel file generated after running the Task_1.ipynb notebook, containing the student data.

Prerequisites
Before running the script, ensure you have the following installed:

Python 3.x

pandas library

You can install pandas using pip:

pip install pandas openpyxl
```openpyxl` is required by pandas to write `.xlsx` files.

## Usage

1.  **Clone the repository** (or download the files):

    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```

2.  **Ensure `Students_data.json` is in the same directory** as `Task_1.ipynb`. You can replace this with your own JSON file, but make sure its structure is compatible (an array of student objects under a "students" key, as shown in `Students_data.json`).

3.  **Run the Jupyter Notebook**:
    You can open and run `Task_1.ipynb` using Jupyter Notebook or JupyterLab:

    ```bash
    jupyter notebook
    ```
    Navigate to `Task_1.ipynb` and run all cells.

    Alternatively, you can extract the Python code from `Task_1.ipynb` into a `.py` file and run it directly:

    ```python
    # Example of how you might extract and run the code as a .py file
    import json
    import pandas as pd

    def load_data(filename):
        """
        Loads JSON data from the specified file.
        """
        with open(filename, "r") as f:
            data = json.load(f)
        return data

    def convert_json_to_excel(json_file, excel_file):
        """
        Converts JSON data from a file into an Excel spreadsheet.
        Assumes the JSON has a top-level key 'students' which is a list of dictionaries.
        """
        data = load_data(json_file)
        data_frame = pd.DataFrame(data['students'])
        data_frame.to_excel(excel_file, index=False)
        print(f"Data successfully written to {excel_file}")

    if __name__ == "__main__":
        json_input_file = "Students_data.json"
        excel_output_file = "Students_data_output.xlsx"
        convert_json_to_excel(json_input_file, excel_output_file)

    ```
    Save the above code as, for example, `json_to_excel.py`, and then run it from your terminal:

    ```bash
    python json_to_excel.py
    ```

4.  **Check the output**: A new Excel file named `Students_data_output.xlsx` will be created in the same directory, containing the converted student data.

## Project Structure


.
├── Task_1.ipynb
├── Students_data.json
└── Students_data_output.xlsx (generated after running the script)


## Contributing

Feel free to fork this repository, make improvements, and submit pull requests.

## License

This project is open source and available under the [MIT License](LICENSE).
