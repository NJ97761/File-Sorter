# File-Sorter
A simple Python script to automatically organize files in a directory into subfolders based on their extension (.pdf, .jpg, etc.).
# Simple File Sorter

A Python script to automatically clean up and organize a directory by moving files into specific folders based on their file type.

## 📜 Description

Do you have a folder (like your "Downloads" folder) that's full of mixed files like PDFs, images, and documents? This script helps you solve that problem. It scans a target directory and automatically moves files into designated subfolders (`pdf files`, `image files`, etc.), keeping your workspace tidy.

## ✨ Key Features

* Scans a specified directory for files.
* Sorts files based on their extension (e.g., `.pdf`, `.jpg`).
* Automatically creates destination folders if they don't already exist.
* Easily customizable to handle more file types.

## 🛠️ Built With

This project uses only standard Python libraries, so no special installations are needed.

* **Python 3**
* **`os` Module:** Used for interacting with the operating system, like listing files and creating directories.
* **`shutil` Module:** Used for high-level file operations, specifically moving files.

## 🚀 How to Use

To get a local copy up and running, follow these simple steps.

### Prerequisites

You just need to have Python 3 installed on your system.

### Instructions

1.  **Clone the repo or download the script**
    ```sh
    git clone [https://github.com/your_username/your_repository.git](https://github.com/your_username/your_repository.git)
    ```
    Or simply download the `File_sorter.ipynb` or `.py` file.

2.  **Configure the path**
    Open the script and change the `path` variable to the absolute path of the folder you want to organize.

    **This is the most important step!**

    ```python
    # BEFORE
    # path = r"C:/Users/Rathore/Documents/ase/"

    # AFTER (example for a Downloads folder)
    path = r"C:/Users/YourUsername/Downloads"
    ```

3.  **Run the script**
    Execute the Python script. It will scan the directory specified in the `path` variable and move the files into their respective folders.

    ```python
    # The core logic of the script
    import os
    import shutil

    # 1. SET THE PATH TO THE DIRECTORY YOU WANT TO ORGANIZE
    path = r"C:/Users/YourUsername/Downloads" # <-- CHANGE THIS LINE

    # 2. Get a list of all files in the directory
    file_name = os.listdir(path)

    # 3. Define the folders you want to create
    folder_names = ['image files', 'pdf files']

    for folder in folder_names:
        folder_path = os.path.join(path, folder)
        if not os.path.exists(folder_path):
            print(f"Creating folder: {folder_path}")
            os.makedirs(folder_path)

    # 4. Move files into the appropriate folders
    for file in file_name:
        if file.endswith(".jpg") or file.endswith(".png"):
            source_path = os.path.join(path, file)
            destination_path = os.path.join(path, "image files", file)
            if not os.path.exists(destination_path):
                shutil.move(source_path, destination_path)
                print(f"Moved {file} to image files")

        elif file.endswith(".pdf"):
            source_path = os.path.join(path, file)
            destination_path = os.path.join(path, "pdf files", file)
            if not os.path.exists(destination_path):
                shutil.move(source_path, destination_path)
                print(f"Moved {file} to pdf files")

    print("File sorting complete!")
    ```

## 🤝 Contributing

Contributions are welcome! If you have ideas for how to improve this script (like adding more file types), feel free to fork the repo and create a pull request.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AddMoreFileTypes`)
3.  Commit your Changes (`git commit -m 'Add support for .docx and .xlsx'`)
4.  Push to the Branch (`git push origin feature/AddMoreFileTypes`)
5.  Open a Pull Request

emai- narendrasingh97761@gmail.com

