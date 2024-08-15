# SubTover

SubTover is a tool for discovering potential subdomain takeovers. It checks the CNAME records of subdomains and verifies if they are pointing to external services that may no longer be in use.

## Features

- **Multi-threaded:** Supports multiple threads for faster scanning.
- **HTTPS support:** Optionally force HTTPS connections during checks.
- **Configurable:** Stores provider data in a configurable directory, with an option to specify a custom path.
- **Verbose output:** Provides detailed information during execution.

## Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/Abhaythakor/SubTover.git
    cd SubTover
    ```

2. **Build the tool:**

    Make sure you have [Go installed](https://golang.org/doc/install).

    ```bash
    go build -o /usr/bin/SubTover main.go
    ```

3. **Set up the configuration directory:**

    By default, SubTover expects the `providers.json` file to be located in `~/.config/SubTover/`. You need to create this directory and copy the `providers.json` file into it:

    ```bash
    mkdir -p ~/.config/SubTover && cp providers/providers.json ~/.config/SubTover
    ```

4. **Run the tool:**

    ```bash
    ./SubTover -l hosts.txt -t 20 -v -o output.txt
    ```

## Usage

### Command-Line Options

- `-l` : **Required**. Specify the list of hosts to check for takeovers.
- `-t` : Number of threads to use (default: 20).
- `-a` : Check all hosts regardless of CNAME.
- `-v` : Show verbose output.
- `-https` : Force HTTPS connections (default: HTTP).
- `-timeout` : Seconds to wait before timeout (default: 10).
- `-o` : File to write enumeration output to.
- `-providers` : Path to the `providers.json` file (optional).

### Example

```bash
./SubTover -l hosts.txt -t 20 -v -o output.txt
```

This command will scan the hosts listed in `hosts.txt`, using 20 threads, and output detailed information to `output.txt`.

## Configuration

### providers.json

The `providers.json` file contains the CNAME and response data for various services. This file is essential for the tool to work correctly.

By default, the tool looks for `providers.json` in the `~/.config/SubTover/` directory. If the file is not found, you will be prompted to provide the path, and it will be copied to the configuration directory for future use.

### Custom `providers.json` Path

You can specify a custom path for the `providers.json` file using the `-providers` flag:

```bash
./SubTover -l hosts.txt -providers /path/to/providers.json
```

## Adding a New Provider

To add a new provider:

1. Open the `providers.json` file located in `~/.config/SubTover/`.
2. Add a new entry with the following structure:

    ```json
    {
        "name": "ProviderName",
        "cname": ["provider.example.com"],
        "response": ["Error message indicating potential takeover"]
    }
    ```

3. Save the file and run the tool again.

## Troubleshooting

### Error: `providers.json not found`

If the tool cannot find the `providers.json` file in the default directory, it will ask you to provide the path. Ensure that the file exists and is in the correct format.



## Contributing

If you'd like to contribute to this project, please fork the repository and use a feature branch. Pull requests are welcome.

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments

- Original tool by [Nizamul Rana (@Ice3man)](https://github.com/Ice3man543/SubOver).
```

### Updates Included:

1. **Configuration Directory Setup**: Added instructions on how to create the `~/.config/SubTover/` directory and copy the `providers.json` file into it:

    ```bash
    mkdir -p ~/.config/SubTover && cp providers/providers.json ~/.config/SubTover
    ```

This ensures that users set up their environment correctly before running the tool.
