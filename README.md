# Cognos Template Propagation Automation

## Table of Contents

- [Overview](#overview)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Scalability](#scalability)
- [Contributing](#contributing)
- [License](#license)

## Overview

This project aims to automate the process of propagating saved custom Cognos templates from one environment to another. It is designed to be scalable and can handle multiple environment pairs simultaneously.

## Prerequisites

- Golang 1.16 or higher
- Access to the environments' databases
- Properly configured `config.json`

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/cognos-template-propagation.git
    ```

2. Navigate to the project directory:

    ```bash
    cd cognos-template-propagation
    ```

3. Build the project:

    ```bash
    go build
    ```

## Configuration

1. Update the `config.json` file with the details of the environments between which you want to propagate Cognos templates. Here's a sample configuration:

    ```json
    {
        "environments": [
            {
                "env1": "Environment1A",
                "env2": "Environment2A",
                "exportPath": "/path/to/exportedA.zip",
                "importPath": "/path/to/importedA.zip",
                "sqlQueries": {
                    "maxTemplateID": "SELECT MAX(TEMPLATE_ID) FROM MN_REPORT_TEMPLATE;",
                    "exportRecords": "Your SQL Export Query A"
                }
            },
            {
                "env1": "Environment1B",
                "env2": "Environment2B",
                "exportPath": "/path/to/exportedB.zip",
                "importPath": "/path/to/importedB.zip",
                "sqlQueries": {
                    "maxTemplateID": "SELECT MAX(TEMPLATE_ID) FROM MN_REPORT_TEMPLATE;",
                    "exportRecords": "Your SQL Export Query B"
                }
            }
        ]
    }
    ```

## Usage

Run the compiled binary:

```bash
./cognos-template-propagation
```

This will start the propagation process based on the configurations provided in `config.json`.

## Scalability

The code is designed to be scalable and can run tasks in parallel using Golang's Goroutines and Channels. This makes it suitable for running in a containerized environment, allowing you to scale the number of instances based on the load.

## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

## License

[MIT](https://choosealicense.com/licenses/mit/)

---

Feel free to modify this README to better suit your project's specific needs. Would you like to add or change anything?
