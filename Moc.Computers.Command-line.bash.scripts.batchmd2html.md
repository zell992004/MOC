---
id: 2dkt32urx8bo4gpa6sv5r9b
title: batchmd2html
desc: ''
updated: 1702828268974
created: 1702828160543
---

``` bash
#!/bin/bash

# Directory containing the Markdown files
input_directory="/path/to/markdown_directory"

# Output directory for the HTML files
output_directory="/path/to/html_directory"

# Convert each Markdown file to HTML
for file in "$input_directory"/*.md; do
    filename=$(basename "$file")
    output_file="$output_directory/${filename%.*}.html"
    pandoc "$file" -o "$output_file"
done

echo "Conversion completed."
```