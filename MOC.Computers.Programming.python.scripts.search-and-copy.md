---
id: vp3lrds8eh57dym1yroah1s
title: search-and-copy
desc: ''
updated: 1702827935678
created: 1702827701008
---

``` python
import os
import shutil

# Get the current directory
current_directory = os.getcwd()

# Function to search for files with the given extension and copy them to the destination directory
def search_and_copy_files(extension, destination_directory):
    for root, _, files in os.walk(current_directory):
        for file in files:
            _, file_extension = os.path.splitext(file)
            if file_extension.lower() == extension.lower():
                source_path = os.path.join(root, file)
                destination_path = os.path.join(destination_directory, file)
                shutil.copy2(source_path, destination_path)
                print(f"Copied '{file}' to '{destination_path}'")

# Prompt the user for the file extension
extension = input("Enter the file extension (without the dot): ")

# Prompt the user for the destination directory
destination_directory = input("Enter the destination directory path: ")

# Verify if the destination directory exists, if not, create it
if not os.path.exists(destination_directory):
    os.makedirs(destination_directory)

# Call the function to search for files with the given extension and copy them to the destination directory
search_and_copy_files(extension, destination_directory)
```