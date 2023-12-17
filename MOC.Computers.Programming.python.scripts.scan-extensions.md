---
id: l9i155hs2mlwhoi9fastiwn
title: scan-extensions
desc: ''
updated: 1702827901392
created: 1702827877322
---


``` python
import os

# Get the current directory
current_directory = os.getcwd()

# Initialize a dictionary to store the extension types
extension_types = {}

# Initialize a counter for the number of directories scanned
num_directories = 0

# Function to scan directories recursively
def scan_directories(directory):
    global num_directories
    for root, _, files in os.walk(directory):
        for file in files:
            _, extension = os.path.splitext(file)
            if extension:
                # Increment the count for the extension type
                extension = extension[1:]  # Remove the leading dot
                extension_types[extension] = extension_types.get(extension, 0) + 1
        num_directories += 1

# Start scanning from the current directory
scan_directories(current_directory)

# Sort the extension types alphabetically
sorted_extensions = sorted(extension_types.items())

# Write the extension types and counts to a text file
output_file = "extension_types.txt"
with open(output_file, "w") as file:
    file.write("Extension\tCount\n")
    file.write("-----------------\n")
    for extension, count in sorted_extensions:
        file.write(f"{extension}\t{count}\n")

# Print the total number of directories scanned
print(f"Total directories scanned: {num_directories}")
```