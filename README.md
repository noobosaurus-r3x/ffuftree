# ffuftree : a Directory Tree Builder for ffuf Output

This is a Python script that builds a directory tree from the JSON output of the ffuf tool. It parses the JSON data, extracts URLs, and their corresponding HTTP status codes, and then prints the directory tree along with the status codes using colored output.

## Requirements

- Python 3.x
- colorama

## Installation

1. Clone the repository to your local machine:
```bash
git clone https://github.com/noobosaurus-r3x/ffuftree
cd ffuftree
```


2. Install the required dependencies:
```bash
pip install colorama
```



## Usage

To use the directory tree builder, you need to provide the path to the JSON file containing the ffuf output. The script will read the file, parse the JSON data, and then print the directory tree with corresponding status codes.

Run the script using the following command:

```bash
python ffuftree.py /path/to/ffuf_output.json
```


Replace `/path/to/ffuf_output.json` with the actual path to your ffuf output JSON file.

## Output

The directory tree will be printed in the console, showing the hierarchical structure of directories and files, along with their HTTP status codes. The status codes will be colorized to make it easier to identify different status ranges:

- Successful (2xx) responses will be displayed in green.
- Redirects (3xx) will be displayed in yellow.
- Client errors (4xx) will be displayed in red.
- Server errors (5xx) will be displayed in blue.

## Example

Suppose your `ffuf_output.json` contains the following data:

```json
{
  "results": [
    {
      "url": "https://example.com/files/document.txt",
      "status": "200",
      "host": "example.com"
    },
    {
      "url": "https://example.com/files/image.jpg",
      "status": "404",
      "host": "example.com"
    },
    {
      "url": "https://example.com/files/music.mp3",
      "status": "200",
      "host": "example.com"
    }
  ]
}
```

Running the script with this JSON file:
```bash
python ffuftree.py ffuf_output.json
```
will output the following:
```bash
└── example.com
    ├── files
       ├── document.txt (Status: 200)
       ├── image.jpg (Status: 404)
       └── music.mp3 (Status: 200)
```

## Ffuf
https://github.com/ffuf/ffuf
