
# SubTover

**SubTover** is a subdomain takeover discovery tool written in Go. It helps you identify vulnerable subdomains that can be taken over due to improper DNS configurations.

## Features

- Detects subdomain takeovers across multiple platforms.
- Configurable through the `providers.json` file.
- Supports multi-threading for faster execution.
- Option to force HTTPS connections.
- Verbose output for detailed information during the scan.

## Installation

### Prerequisites

- Go 1.23.0 or later installed on your system.
- Git installed on your system.

### Install via `go install`

You can install the tool directly from the GitHub repository:

```bash
go install github.com/Abhaythakor/SubTover@latest
```

Replace `Abhaythakor` with your actual GitHub username.

### Clone and Build from Source

Alternatively, you can clone the repository and build it yourself:

1. Clone the repository:

   ```bash
   git clone https://github.com/Abhaythakor/SubTover.git
   cd SubTover
   ```

2. Build the binary:

   ```bash
   go build -o SubTover
   ```

3. Run the tool:

   ```bash
   ./SubTover -h
   ```

## Usage

```
SubTover v.1.2             
==================================================

Usage: SubTover [options]

Options:
  -t int
        Number of threads to use (default 20)
  -l string
        List of hosts to check takeovers on
  -a    Check all hosts regardless of CNAME
  -v    Show verbose output
  -https
        Force HTTPS connections (Default: http://)
  -timeout int
        Seconds to wait before timeout (default 10)
  -o string
        File to write enumeration output to
```

### Example Command

To run the tool on a list of hosts:

```bash
./SubTover -l hosts.txt -t 30 -v -https
```

This command checks the subdomains listed in `hosts.txt` using 30 threads, forces HTTPS connections, and provides verbose output.




You can add more providers by extending this file.

## Contributing

Contributions are welcome! If you want to add more providers, improve the code, or fix bugs, feel free to open an issue or submit a pull request.

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Make your changes and commit them.
4. Push your changes to your fork.
5. Submit a pull request to the `main` branch.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Nizamul Rana (@Ice3man) for the original idea and implementation.
- [parnurzeal/gorequest](https://github.com/parnurzeal/gorequest) for making HTTP requests simpler.
```

### Replace Placeholders

Make sure to replace `Abhaythakor` with your actual GitHub username in the installation instructions and any other sections where it appears.

### Key Sections in the README

- **Project Description:** Brief explanation of what the tool does.
- **Features:** List of key features.
- **Installation:** Instructions on how to install the tool via `go install` or by cloning and building from source.
- **Usage:** Command-line options and example usage.
- **Configuration:** Explanation of the `providers.json` file.
- **Contributing:** Instructions on how to contribute to the project.
- **License:** Information about the project's licensing.
- **Acknowledgements:** Credit to the original creator and any libraries used.

This `README.md` provides comprehensive guidance for users and contributors, ensuring they can easily install, use, and contribute to the `SubTover` project.