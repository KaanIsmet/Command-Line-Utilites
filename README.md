# Command Line Utilities Collection

A collection of useful C++ command line utilities for Linux systems. Each utility is designed to be lightweight, efficient, and easy to use from the terminal.

## 🛠️ Utilities Included

### File Management
- **`fileorg`** - Organize files in directories by type, date, or size
- **`textstats`** - Analyze text files for word count, line count, and character statistics
- **`filefind`** - Advanced file search utility with pattern matching
- **`dirsize`** - Analyze disk usage by directory with visual representation

### System Tools
- **`dirtree`** - Display directory structure in a tree format
- **`logparse`** - Extract and filter information from log files
- **`sysmon`** - Monitor system resources (CPU, memory, disk)

### Utilities
- **`calc`** - Advanced command line calculator with math functions
- **`passgen`** - Generate secure passwords with customizable criteria
- **`unitconv`** - Convert between various units (temperature, distance, weight, etc.)

## 🚀 Quick Start

### Prerequisites
- Linux operating system
- GCC compiler with C++17 support
- Make (optional, for easier building)

### Installation

1. **Clone the repository:**
   ```bash
   git clone <repository-url>
   cd command-line-utilities
   ```

2. **Build all utilities:**
   ```bash
   make all
   ```

3. **Install to your personal bin directory:**
   ```bash
   make install
   ```

4. **Add to PATH (if not already done):**
   ```bash
   echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc
   source ~/.bashrc
   ```

### Manual Installation

For individual utilities:
```bash
# Compile
g++ -std=c++17 -O2 -o utility_name src/utility_name.cpp

# Make executable
chmod +x utility_name

# Move to bin directory
mv utility_name ~/bin/
```

## 📚 Usage Examples

### File Organizer (`fileorg`)
```bash
# Organize current directory by file type
fileorg --type

# Organize by date modified
fileorg --date /path/to/directory

# Organize by file size
fileorg --size --ascending
```

### Text Statistics (`textstats`)
```bash
# Analyze a single file
textstats document.txt

# Analyze multiple files
textstats *.txt

# Get detailed statistics
textstats --detailed report.md
```

### Password Generator (`passgen`)
```bash
# Generate default password
passgen

# Generate 16-character password with symbols
passgen --length 16 --symbols

# Generate multiple passwords
passgen --count 5 --length 12
```

### Unit Converter (`unitconv`)
```bash
# Temperature conversion
unitconv temp 32 F C

# Distance conversion
unitconv distance 100 km miles

# Weight conversion
unitconv weight 10 kg lbs
```

### Calculator (`calc`)
```bash
# Basic arithmetic
calc "2 + 3 * 4"

# Advanced functions
calc "sin(pi/2)"

# Interactive mode
calc --interactive
```

## 🔧 Building from Source

### System Requirements
- GCC 7.0+ or Clang 5.0+
- CMake 3.10+ (optional)
- Linux kernel 3.2+

### Build Options

**Using Make:**
```bash
# Build all utilities
make all

# Build specific utility
make fileorg

# Build with debug symbols
make DEBUG=1

# Clean build files
make clean
```

**Using CMake:**
```bash
mkdir build && cd build
cmake ..
make
```

### Compilation Flags
- `-std=c++17`: C++17 standard support
- `-O2`: Optimization level 2
- `-Wall`: Enable all warnings
- `-Wextra`: Extra warning flags

## 📋 Configuration

Some utilities support configuration files located in `~/.config/cli-utils/`:

### `config.ini`
```ini
[fileorg]
default_sort=type
show_hidden=false

[passgen]
default_length=12
include_symbols=true

[textstats]
show_detailed=false
```

### Environment Variables
- `CLI_UTILS_CONFIG`: Override default config directory
- `CLI_UTILS_TEMP`: Temporary directory for operations

## 🧪 Testing

Run the test suite:
```bash
make test
```

Run specific utility tests:
```bash
./tests/test_fileorg
./tests/test_calculator
```

## 📖 Documentation

Each utility includes built-in help:
```bash
utility_name --help
utility_name -h
```

For detailed documentation, see the `docs/` directory:
- [File Organizer Guide](docs/fileorg.md)
- [Calculator Functions](docs/calculator.md)
- [Advanced Usage](docs/advanced.md)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature-name`
3. Make your changes and add tests
4. Ensure all tests pass: `make test`
5. Commit your changes: `git commit -am 'Add feature'`
6. Push to the branch: `git push origin feature-name`
7. Submit a pull request

### Code Style
- Follow Google C++ Style Guide
- Use meaningful variable names
- Add comments for complex logic
- Include error handling

## 🐛 Troubleshooting

**Permission denied errors:**
```bash
chmod +x ~/bin/utility_name
```

**Command not found:**
```bash
echo $PATH
# Make sure ~/bin is in your PATH
```

**Compilation errors:**
```bash
# Check GCC version
gcc --version

# Install development tools
sudo apt install build-essential  # Ubuntu/Debian
sudo yum groupinstall "Development Tools"  # CentOS/RHEL
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Inspired by classic UNIX utilities
- Built with modern C++ best practices
- Community contributions and feedback

## 📞 Support

- Create an issue for bug reports
- Use discussions for questions
- Check the wiki for additional examples

---

**Version:** 1.0.0  
**Last Updated:** June 2025  
**Compatibility:** Linux (Ubuntu 18.04+, CentOS 7+, Fedora 28+)
