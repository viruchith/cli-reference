### Command-Line Utilities & Tools

#### `cheat`

An interactive command-line tool that allows you to create and view text-based cheat sheets. It is designed to remind you of command arguments you use frequently but can’t quite memorize.

```bash
# View the built-in cheat sheet for the 'tar' command
cheat tar

# Edit your personal custom cheat sheet for 'git'
cheat -e git
```

#### `clamav`

An open-source antivirus engine designed for detecting trojans, viruses, malware, and other malicious threats, primarily used on mail gateways but perfectly functional for local directories.

```bash
# Scan a specific directory and only print infected files
clamscan -r --infected ~/Downloads

# Update the virus signature database
freshclam
```

#### `container`

Apple's command-line interface for creating and managing containers on macOS. It provides subcommands to run container workloads, inspect images, and manage local container resources.

```bash
# Show all available container subcommands and flags
container --help

# Run a container image and execute a command inside it
container run --rm alpine:latest echo "hello from apple container"
```

#### `coreutils`

The GNU core utilities. This package installs the basic file, shell, and text manipulation utilities of the GNU operating system (like `ls`, `cat`, and `chmod`). On macOS, they are usually prefixed with a `g` to prevent overriding native tools.

```bash
# Use the GNU version of 'ls' with full color formatting
gls --color=auto

# Display disk usage in a human-readable format via GNU 'df'
gdf -h
```

#### `fd`

A simple, fast, and user-friendly alternative to the traditional `find` command. It uses sensible defaults (like ignoring hidden files and `.gitignore` paths) and features colorized output.

```bash
# Search for all Markdown files containing the word "invoice"
fd invoice -e md

# Search for a specific directory name across the entire file system
fd --type d "project-assets"
```

#### `fzf`

A general-purpose, blazing-fast command-line fuzzy finder. It lets you filter down lists of files, command histories, hostnames, or process IDs interactively as you type.

```bash
# Interactively search files in the current folder and open the selection in Vim
vim $(fzf)

# Search through your command history fuzzy-style
history | fzf
```

#### `gh`

The official GitHub Command Line Interface. It brings pull requests, issues, repository configurations, and GitHub Actions directly to your terminal.

```bash
# Clone a GitHub repository using just the "username/repo" shorthand
gh repo clone octocat/Spoon-Knife

# View a list of open issues assigned to you in the current repository
gh issue list --assignee "@me"
```

#### `glab`

An open-source GitLab CLI tool that brings GitLab pull requests, issues, releases, and pipelines straight to your terminal.

```bash
# Check the status of the current repository's GitLab CI/CD pipeline
glab pipeline status

# List open merge requests with a specific label
glab mr list --label "bug"
```

#### `htop`

An interactive, real-time process viewer and system monitor. It provides a more colorful, readable, and dynamic breakdown of CPU, memory, and running tasks than the standard `top`.

```bash
# Launch the monitor directly
htop

# Launch htop showing only processes owned by a specific user
htop -u username
```

#### `httpie`

A user-friendly, command-line HTTP client meant as a modern alternative to `curl`. It features intuitive syntax, formatted/colorized JSON outputs, and easy file uploads.

```bash
# Send a standard GET request to an API endpoint
http https://api.github.com/users/octocat

# Send a POST request with JSON data payload
http POST https://httpbin.org/post name=John email=john@example.com
```

#### `apktool`

A reverse engineering tool for Android applications. It can decode resources to their original form, rebuild them, and debug `smali` code, making it essential for custom ROMs, localizing apps, and analyzing closed-source applications.

```bash
# Decode an APK file into a human-readable format (resources, Smali, etc.)
apktool d my_application.apk -o decoded_app

# Build an APK from a decoded application directory
apktool b decoded_app -o rebuilt_app.apk

# Decode an APK without disassembling DEX files (no Smali code)
apktool d my_application.apk -r -o decoded_no_smali

# Decode an APK without decoding resources (keeps resources as binary)
apktool d my_application.apk -s -o decoded_no_resources

# Install a framework file for a specific Android version (e.g., AOSP)
apktool if framework-res.apk

# Show help for all available apktool commands and options
apktool --help
```

#### `aria2` (`aria2c`)

An ultra-fast, lightweight, multi-protocol and multi-source command-line download utility. It supports HTTP/HTTPS, FTP, SFTP, BitTorrent, and Metalink. `aria2` can download a single file from multiple sources or mirrors simultaneously, and split downloads into multiple segments to maximize available bandwidth utilization.

```bash
# Download a file from a single URL and specify a custom output filename (-o)
aria2c -o custom_file.zip "https://example.com/file.zip"

# Accelerate download using multiple connections (-s) and max connections per server (-x)
aria2c -s 16 -x 16 -k 1M "https://example.com/largefile.iso"

# Download a file simultaneously from multiple mirror URLs
aria2c "https://mirror1.example.com/file.iso" "https://mirror2.example.com/file.iso"

# Resume an interrupted or incomplete download (-c / --continue)
aria2c -c "https://example.com/largefile.zip"

# Batch download multiple URLs listed in a text file (-i) with concurrent download limit (-j)
aria2c -i urls.txt -j 4

# Restrict download and upload speed limits (--max-download-limit, --max-upload-limit)
aria2c --max-download-limit=5M --max-upload-limit=500k "https://example.com/file.zip"

# Download via BitTorrent file or Magnet link (and stop seeding upon completion)
aria2c --seed-time=0 "https://example.com/ubuntu.torrent"
aria2c --seed-time=0 "magnet:?xt=urn:btih:EXAMPLEHASH..."

# View files inside a torrent and their index numbers without downloading (-S)
aria2c -S file.torrent

# Download specific files from a multi-file BitTorrent transfer by index (--select-file)
aria2c --select-file=1,3-5 file.torrent

# Download with HTTP basic authentication and custom request headers
aria2c --http-user="username" --http-passwd="password" --header="Authorization: Bearer token" "https://example.com/protected.zip"

# Run aria2 as a background RPC daemon for web UIs (e.g., AriaNg, webui-aria2)
aria2c --enable-rpc --rpc-listen-all=true --rpc-secret="mysecret" -D

# Load options from a custom configuration file (--conf-path)
aria2c --conf-path=~/.config/aria2/aria2.conf
```

#### `jq`

A lightweight and flexible command-line JSON processor. It lets you slice, filter, map, and transform structured JSON data with ease.

```bash
# Extract and pretty-print a specific key from a JSON payload
curl -s https://api.github.com/repos/stedolan/jq | jq '.description'

# Map an array of objects to filter out only specific fields
cat data.json | jq '[.[] | {name: .name, active: .status}]'
```

#### `jadx`

A DEX to Java decompiler. It allows you to decompile Android `.apk` files, `dex` files, or `jar` files into readable Java source code, providing a powerful tool for reverse engineering and security analysis.

```bash
# Decompile an APK file to a specified output directory
jadx -d output_dir my_application.apk

# Decompile a DEX file and save the output as Java files in a directory
jadx -d output_dir classes.dex

# Decompile an APK and save resources (like XML, images) in the output directory
jadx -r -d output_with_resources my_application.apk

# Decompile an APK with verbose logging and include debug information
jadx --verbose --debug -d debug_output_dir my_application.apk

# Show help for all available jadx commands and options
jadx --help
```

#### `lnav`

The Log File Navigator, an advanced log file viewer for the terminal. It automatically uncompresses, parses, and formats logs, letting you merge different log files chronologically.

```bash
# View and automatically watch system log entries in real-time
lnav /var/log/system.log

# Open multiple log files zipped up in a directory simultaneously
lnav ~/logs/*.gz
```

#### `nmap`

A powerful network exploration tool and security/port scanner. It is widely used for network inventory, managing service upgrade schedules, and monitoring host or service uptime.

```bash
# Scan the 1000 most common ports on a target IP address safely
nmap 192.168.1.1

# Aggressively scan a host to detect the operating system and running service versions
nmap -A target-hostname.com
```

#### `pandoc`

The "swiss-army knife" of document conversion. It converts files from one markup format into another (e.g., Markdown, HTML, LaTeX, Word DOCX, PDF, or EPUB).

```bash
# Convert a Markdown file into a clean standalone HTML page
pandoc document.md -s -o index.html

# Convert a Markdown document into a Microsoft Word file (.docx)
pandoc notes.md -o output.docx
```

#### `rclone`

A versatile command-line program to manage, sync, configure, and back up files to and from cloud storage buckets (like Google Drive, S3, Dropbox, and OneDrive).

```bash
# Safely copy a local directory up to a configured Google Drive destination
rclone copy ~/Documents mygdrive:Backup/Documents

# Sync a local directory with an AWS S3 bucket (deletes files on remote if missing locally)
rclone sync ~/Photos mys3bucket:personal-photos --interactive
```

#### `ripgrep` (`rg`)

A line-oriented search tool that recursively searches your current directory for a regex pattern. It is significantly faster than standard `grep` and respects `.gitignore` rules by default.

```bash
# Search for a word recursively across all files, ignoring case
rg -i "todo: fix this"

# Search for a string matching only within Python scripts
rg "import requests" -g "*.py"
```

#### `shellcheck`

A static analysis tool for shell scripts. It finds bugs, syntax issues, and stylistic quirks in your `bash` or `sh` scripts, offering concrete suggestions to fix them.

```bash
# Analyze a shell script for potential edge cases or errors
shellcheck deploy.sh

# Run shellcheck outputting the findings in a specific JSON format
shellcheck -f json backup.sh
```

#### `semgrep`

A fast, open-source, static analysis tool that finds bugs and enforces code standards. It supports many languages and allows you to write custom rules.

```bash
# Scan the current directory using the default registry rules
semgrep scan

# Scan a project using a specific rule or ruleset
semgrep scan --config="p/python"
```

#### `sniffnet`

A cross-platform CLI application to comfortably monitor your network traffic activity, bandwidth intensity, and application protocols in real-time.

```bash
# Launch the application interface directly in your shell
sniffnet
```

#### `superfile` (`spf`)

A modern terminal file manager with a keyboard-first interface, fast navigation, and built-in operations for browsing and managing files from the command line.

```bash
# Launch Superfile in the current directory
spf

# Show available flags and subcommands
spf --help
```

#### `syncthing`

A continuous file synchronization program that syncs files between two or more computers in a secure, decentralized (peer-to-peer) manner.

```bash
# Start the syncthing daemon background process and open the local web UI configuration
syncthing

# Run syncthing without launching the browser window interface automatically
syncthing --no-browser
```

#### `unar`

A command-line tool for extracting files from a massive variety of archive formats (like RAR, 7z, Zip, Tar, and more). It behaves much more consistently with non-ASCII file names than standard unzippers.

```bash
# Extract the contents of an archive file into the current directory
unar archive.rar

# Extract an archive while specifying a password
unar -p secret password_protected.7z
```

#### `wget`

A non-interactive network downloader used to retrieve files from the web via HTTP, HTTPS, and FTP. It easily handles background downloads and recursive directory mirrors.

```bash
# Download a file directly to your current folder
wget https://example.com/file.zip

# Recursively mirror a whole website for offline reading, ignoring parent directories
wget --mirror --convert-links --page-requisites https://example.com
```

#### `zoxide` (`z`)

A smarter `cd` replacement that remembers the directories you visit and lets you jump to them quickly using the `z` command with fuzzy matching.

```bash
# Jump to the most likely directory matching "proj"
z proj

# Interactively pick a match when multiple directories are possible
zi
```

---

### Development Language Runtimes & Package Managers

#### `node` / `node@24`

The JavaScript runtime environment built on Chrome's V8 engine, executing JS outside a web browser. `node` grabs the current stable version, while `node@24` explicitly targets version 24.

```bash
# Run a specific JavaScript file locally
node index.js

# Launch the interactive Read-Eval-Print Loop (REPL) shell
node
```

#### `nvm`

Node Version Manager. A shell script tool utilized to manage, install, and hot-swap between multiple running versions of Node.js on the same machine.

```bash
# Install and switch your active environment to Node.js version 20
nvm install 20

# Swap your shell environment back to utilizing your installed Node v18
nvm use 18
```

#### `pnpm`

A fast, disk-space-efficient package manager for Node.js. It saves dependencies into a global content-addressable store on your machine and links them to projects using hard links, saving massive amounts of storage space.

```bash
# Install all target dependencies listed inside your package.json
pnpm install

# Add a specific development package to your active project
pnpm add -D typescript
```

#### `podman`

A daemonless container engine for developing, managing, and running OCI (Open Container Initiative) containers and pods on your system. It is designed as a drop-in, rootless alternative to Docker.

```bash
# Download and spin up an Nginx container without needing root privileges
podman run -d -p 8080:80 nginx

# Build an environment container image using a local Containerfile or Dockerfile
podman build -t my-app:latest .
```

#### `python@3.14`

The runtime environment for the Python programming language, specifically locked to the 3.14 lifecycle branch.

```bash
# Execute a localized script file
python3.14 script.py

# Launch the interactive Python 3.14 development shell
python3.14
```

#### `uv`

An extremely fast Python package installer and resolver written in Rust. It functions as a drop-in replacement for `pip`, `pip-tools`, and `virtualenv`, processing operations multiple times faster.

```bash
# Instantly create a clean, localized Python virtual environment
uv venv

# Force-install a specific package dependency at high speed
uv pip install requests
```

#### `pyenv`

Python Version Manager (`pyenv`) lets you easily install, manage, and switch between multiple versions of Python. It operates by injecting a directory of executable shims (`~/.pyenv/shims`) at the beginning of your `PATH`. When you run `python`, `pip`, or a Python CLI entrypoint, the shim determines which Python version to invoke based on shell environment variables (`PYENV_VERSION`), per-directory `.python-version` files, or the machine-wide global setting.

`pyenv` builds Python runtimes directly from source via `python-build` (supporting CPython, PyPy, GraalPython, Anaconda, and Miniconda) and integrates with the `pyenv-virtualenv` plugin to create isolated per-project virtual environments.

```bash
# ---------------------------------------------------------
# Installation & Shell Configuration
# ---------------------------------------------------------
# Install pyenv via Homebrew (macOS) or pyenv-installer script (Linux)
brew install pyenv pyenv-virtualenv
# or: curl https://pyenv.run | bash

# Add pyenv to your shell environment (~/.zshrc or ~/.bashrc)
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"

# macOS prerequisite build dependencies via Homebrew:
# brew install openssl readline sqlite3 xz zlib tcl-tk

# Linux (Debian/Ubuntu) prerequisite build dependencies:
# sudo apt update && sudo apt install -y build-essential libssl-dev zlib1g-dev \
#   libbz2-dev libreadline-dev libsqlite3-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev

# ---------------------------------------------------------
# Inspecting Available Python Versions
# ---------------------------------------------------------
# List all available Python releases installable via pyenv
pyenv install --list

# Filter available Python versions matching specific major releases
pyenv install -l | grep -E "^\s*3\.(11|12|13)"

# List available alternative runtimes (PyPy, Anaconda, Stackless)
pyenv install -l | grep -E "(pypy|miniconda)"

# ---------------------------------------------------------
# Installing & Compiling Python Runtimes
# ---------------------------------------------------------
# Install a specific CPython release compiled from source
pyenv install 3.12.2
pyenv install 3.11.8

# Install with custom compilation flags (e.g., shared library support or optimization)
env PYTHON_CONFIGURE_OPTS="--enable-shared --enable-optimizations" pyenv install 3.12.2

# Install PyPy (JIT-compiled Python) or Miniconda distribution
pyenv install pypy3.10-7.3.15
pyenv install miniconda3-latest

# Uninstall an installed Python version to free up disk space
pyenv uninstall 3.10.12

# ---------------------------------------------------------
# Listing & Viewing Versions
# ---------------------------------------------------------
# List all installed Python versions managed by pyenv (active version marked with *)
pyenv versions

# Show the currently active Python version and the config file setting it
pyenv version

# Locate the absolute filesystem path to the active binary
pyenv which python
pyenv which pip
pyenv which pytest

# Print the installation prefix directory for a specific version
pyenv prefix
pyenv prefix 3.12.2

# ---------------------------------------------------------
# Switching Versions (Global, Local, Shell)
# ---------------------------------------------------------
# Set the machine-wide global default Python version
pyenv global 3.12.2

# Set a project-specific Python version (writes to local .python-version file)
pyenv local 3.11.8

# Set multiple versions simultaneously (essential for testing across versions with tox)
pyenv local 3.12.2 3.11.8 3.10.13

# Set a temporary Python version for the current shell session only
pyenv shell 3.12.2

# Unset shell or local version overrides
pyenv shell --unset
rm -f .python-version

# Rehash pyenv shims (run after installing new CLI packages with pip like black, ruff, etc.)
pyenv rehash

# Run a command inside a specific Python environment without changing current version
pyenv exec python --version
pyenv exec pip list

# ---------------------------------------------------------
# Virtual Environment Management (pyenv-virtualenv)
# ---------------------------------------------------------
# Create an isolated virtual environment based on an installed Python version
pyenv virtualenv 3.12.2 my-api-env

# List all virtual environments managed by pyenv
pyenv virtualenvs

# Bind the current directory to the virtual environment (auto-activates when entering directory)
pyenv local my-api-env

# Manually activate or deactivate the virtual environment in current shell
pyenv activate my-api-env
pyenv deactivate

# Delete an obsolete virtual environment
pyenv virtualenv-delete my-api-env

# ---------------------------------------------------------
# Maintenance & Updates
# ---------------------------------------------------------
# Update pyenv and python-build definitions to get access to newly released Python versions
pyenv update
# (Or if installed via git clone: git -C $(pyenv root) pull)
```

#### `sdkman` (`sdk`)

Software Development Kit Manager (SDKMAN!) is a CLI tool for managing parallel versions of multiple Software Development Kits on Unix-based systems (macOS, Linux, WSL). While widely recognized as the standard version manager for the JVM ecosystem (managing OpenJDK distributions like Eclipse Temurin, Amazon Corretto, Azul Zulu, GraalVM, BellSoft Liberica), it also manages build tools, languages, and CLI frameworks including Gradle, Maven, Kotlin, Scala, Groovy, Micronaut, Quarkus, Spring Boot CLI, and VisualVM.

SDKMAN handles downloading, unpacking, switching shell symlinks, setting `PATH` and `*_HOME` environment variables, and supports directory-level environment switching via `.sdkmanrc` files.

```bash
# ---------------------------------------------------------
# Installation & Initialization
# ---------------------------------------------------------
# Install SDKMAN via the official curl installer script
curl -s "https://get.sdkman.io" | bash

# Initialize SDKMAN in the current shell session (or add to ~/.zshrc / ~/.bashrc)
source "$HOME/.sdkman/bin/sdkman-init.sh"

# Verify SDKMAN installation and display the installed version
sdk version

# Display full command help and available options
sdk help

# ---------------------------------------------------------
# Discovery & Candidate Inspection
# ---------------------------------------------------------
# List all available SDK candidates (Java, Gradle, Maven, Kotlin, etc.)
sdk list

# List all available versions and distributions for a specific candidate (e.g., Java)
sdk list java

# List available versions for build tools and languages
sdk list gradle
sdk list maven
sdk list kotlin

# ---------------------------------------------------------
# Installing SDKs & Versions
# ---------------------------------------------------------
# Install the latest stable default version of a candidate
sdk install gradle
sdk install maven

# Install a specific Java distribution and version (e.g., Eclipse Temurin JDK 21)
sdk install java 21.0.2-tem

# Install Amazon Corretto or Azul Zulu Java LTS releases
sdk install java 17.0.10-amzn
sdk install java 17.0.10-zulu

# Install GraalVM Community Edition for native image compilation
sdk install java 21.0.2-graalce

# Install a specific version of Gradle or Maven
sdk install gradle 8.6
sdk install maven 3.9.6

# Register an existing local Java installation (e.g., Apple Silicon macOS native JDK)
sdk install java local-jdk21 /Library/Java/JavaVirtualMachines/temurin-21.jdk/Contents/Home

# ---------------------------------------------------------
# Switching & Active Version Management
# ---------------------------------------------------------
# Switch to a specific version for the current shell session only
sdk use java 17.0.10-tem
sdk use gradle 8.5

# Set a candidate version as the global machine default
sdk default java 21.0.2-tem
sdk default maven 3.9.6

# Display the currently active version of all candidates
sdk current

# Display the currently active version for a specific candidate
sdk current java
sdk current gradle

# Print the installation path of a candidate version (useful for scripting JAVA_HOME)
sdk home java 21.0.2-tem
export JAVA_HOME=$(sdk home java 21.0.2-tem)

# ---------------------------------------------------------
# Project-Specific Configuration (.sdkmanrc)
# ---------------------------------------------------------
# Generate a .sdkmanrc file in the current directory with current SDK versions
sdk env init

# Switch the shell environment to match the versions specified in .sdkmanrc
sdk env

# Reset candidate versions back to their global defaults after leaving project
sdk env clear

# Tip: Enable automatic switching on cd by setting `sdkman_auto_env=true` in ~/.sdkman/etc/config

# ---------------------------------------------------------
# Upgrades, Uninstallation & Maintenance
# ---------------------------------------------------------
# Fetch the latest candidate lists and available version metadata from SDKMAN servers
sdk update

# Check for outdated candidates and interactively upgrade them
sdk upgrade

# Upgrade a specific candidate to its latest available version
sdk upgrade gradle

# Update the SDKMAN CLI itself to the latest release
sdk selfupdate
sdk selfupdate force

# Uninstall an installed version of a candidate
sdk uninstall java 11.0.22-tem
sdk uninstall gradle 7.6.4

# Enable or disable offline mode when working without internet connectivity
sdk offline enable
sdk offline disable

# Clear cached candidate archives, temporary downloads, and broadcast caches
sdk flush archives
sdk flush temp
sdk flush candidates
```

#### `jenv`

Java Environment Manager (`jenv`) is a CLI tool modeled after `rbenv` and `pyenv` designed to seamlessly manage and switch between multiple Java Development Kits (JDKs) on macOS and Linux. Unlike SDKMAN, `jenv` does not download or install JDKs itself; instead, it registers existing JDK installations already present on your system (such as JDKs installed via Homebrew, macOS `/Library/Java/JavaVirtualMachines`, Linux package managers, or direct archive downloads) and dynamically switches between them using shell shims (`~/.jenv/shims`).

`jenv` manages `JAVA_HOME` export, per-directory version files (`.java-version`), and offers plugins for seamless integration with build systems like Maven, Gradle, SBT, and Ant.

```bash
# ---------------------------------------------------------
# Installation & Shell Setup
# ---------------------------------------------------------
# Install jenv via Homebrew (macOS)
brew install jenv

# Add jenv shims and autocompletion to your shell configuration (~/.zshrc or ~/.bashrc)
export PATH="$HOME/.jenv/bin:$PATH"
eval "$(jenv init -)"

# Reload your shell configuration
source ~/.zshrc

# Run diagnostics to check for common environment or shim configuration issues
jenv doctor

# ---------------------------------------------------------
# Adding & Registering Existing JDKs
# ---------------------------------------------------------
# Add a macOS system-installed JDK from /Library/Java/JavaVirtualMachines/
jenv add /Library/Java/JavaVirtualMachines/temurin-21.jdk/Contents/Home
jenv add /Library/Java/JavaVirtualMachines/temurin-17.jdk/Contents/Home

# Add a Homebrew-installed OpenJDK on macOS
jenv add $(brew --prefix openjdk@17)/libexec/openjdk.jdk/Contents/Home
jenv add $(brew --prefix openjdk@21)/libexec/openjdk.jdk/Contents/Home

# Add a Linux system JDK from /usr/lib/jvm/
jenv add /usr/lib/jvm/java-17-openjdk-amd64
jenv add /usr/lib/jvm/java-21-openjdk-amd64

# Add an SDKMAN-downloaded JDK into jenv management
jenv add ~/.sdkman/candidates/java/21.0.2-tem

# ---------------------------------------------------------
# Listing & Viewing Versions
# ---------------------------------------------------------
# List all JDK versions registered in jenv (active version marked with *)
jenv versions

# Show the currently active Java version and the scope where it was set
jenv version

# Show which actual executable binary is being invoked by the shim
jenv which java
jenv which javac

# Print the directory path of the active JDK (equivalent to JDK home)
jenv prefix
jenv javahome

# ---------------------------------------------------------
# Switching Java Versions (Global, Local, Shell)
# ---------------------------------------------------------
# Set the machine-wide global Java version
jenv global 21.0
# Or use full alias / vendor name:
jenv global temurin64-21.0.2

# Set a project-specific Java version (creates a .java-version file in current dir)
jenv local 17.0

# Set a temporary Java version for the current terminal session only
jenv shell 11.0

# Unset the local directory or shell-specific version override
jenv local --unset
jenv shell --unset

# Execute a command directly using a specific Java version without switching
jenv exec java -jar application.jar

# ---------------------------------------------------------
# Essential Plugins (JAVA_HOME & Build Tool Integration)
# ---------------------------------------------------------
# Enable the export plugin to automatically sync and export JAVA_HOME variable
jenv enable-plugin export

# Enable build tool plugins so Maven, Gradle, Ant, and SBT respect the active JDK
jenv enable-plugin maven
jenv enable-plugin gradle
jenv enable-plugin sbt

# List all available and enabled jenv plugins
jenv plugins

# Disable a previously enabled plugin
jenv disable-plugin maven

# ---------------------------------------------------------
# Managing JDK Aliases & Removal
# ---------------------------------------------------------
# Remove an uninstalled or deprecated JDK version from jenv registry
jenv remove 17.0.2
jenv remove temurin64-17.0.2
```

#### `shasum` / `sha256sum` / `sha512sum`

Utilities used to calculate and verify SHA cryptographic hashes to ensure file integrity.

```bash
# Generate a SHA-256 checksum for a downloaded file
sha256sum large-dataset.zip

# Verify a file matches a previously recorded checksum file
sha256sum -c checksums.txt
```

#### `seq`

A simple utility that prints a sequence of numbers incrementing from a start value to an end value.

```bash
# Print numbers from 1 to 10
seq 1 10

# Print odd numbers from 1 to 20 (incrementing by 2)
seq 1 2 20
```

#### `networkQuality`

A modern built-in macOS command-line utility that runs a network benchmark test, measuring your download/upload capacity alongside your network responsiveness (RPM - Round-trips Per Minute).

```bash
# Run a standard network quality test
networkQuality

# Run a parallel execution test checking both IPv4 and IPv6 streams
networkQuality -p
```

#### `javap`

The Java Class File Disassembler. It opens compiled Java .class files and prints their fields, constructors, methods, and bytecode instructions.

```bash
# View the public method signatures and fields of a compiled Java class
javap MyController.class

# Disassemble the class file to inspect the actual raw JVM bytecode instructions
javap -c ParallelWorker.class
```

#### `iperf3-darwin`

A network bandwidth measurement tool. It generates traffic between a client machine and an active listening instance to pinpoint your true point-to-point network limits.

```bash
# Set your terminal to act as the listening performance test server
iperf3 -s

# Run a 10-second upload/download test against a remote server IP address
iperf3 -c 192.168.1.50
```

#### `textutil`

A built-in macOS command-line utility for manipulating text documents in various formats.

```bash
# Convert a Microsoft Word document to a clean plain text file
textutil -convert txt legacy_notes.docx

# Convert an HTML file into a standard Rich Text Format (RTF) document
textutil -convert rtf index.html -output structured_notes.rtf

# Convert an RTF file into a standalone HTML webpage
textutil -convert html document.rtf

# Strip formatting from a Rich Text document, modifying the file inline
textutil -convert txt styling.rtf

# Combine multiple text, HTML, or Word files into a single master document
textutil -cat docx chapter1.txt chapter2.html chapter3.docx -output book.docx

# Display structural layout information and metadata of a target file
textutil -info resume.docx

# Extract and set specific metadata tags inside a document
textutil -setmetadata "Author=Jane Doe" "Keywords=Report, Final" brief.rtf

# Force the output encoding to UTF-8 when converting a file
textutil -convert txt raw_data.html -encoding UTF-8
```

---

### Media & Imaging Processing (`ffmpeg`, `imagemagick`, etc.)

#### `ffmpeg`

The ultimate command-line framework for video, audio, and multimedia processing.

```bash
# Extract audio from a video file and save it as a high-quality MP3
ffmpeg -i video.mp4 -q:a 0 -map a audio.mp3

# Compress a heavy video file using the modern H.265 (HEVC) codec
ffmpeg -i input.mov -vcodec libx265 -crf 28 compressed_output.mp4
```

#### `ffprobe`

A tool used to gather structural information, stream details, and metadata from multimedia streams.

```bash
# View all metadata and format info of a media file in a clean JSON structure
ffprobe -v quiet -print_format json -show_format -show_streams video.mkv
```

#### `ffplay`

A minimal, portable media player utilizing the FFmpeg libraries.

```bash
# Play back a raw video stream directly from your terminal layout
ffplay video.mp4

# Display an audio file visualizer alongside playback
ffplay -showmode 1 music.mp3
```

#### `convert` (ImageMagick)

The core ImageMagick utility for converting, resizing, and heavily modifying images.

```bash
# Scale down an image to a specific width while keeping its aspect ratio
convert banner.png -resize 800x photo_scaled.png

# Batch convert a whole directory of PNGs into compressed JPEGs
convert *.png -set filename:f "%t" -quality 85 "%[filename:f].jpg"
```

#### `mogrify` (ImageMagick)

Similar to `convert`, but explicitly designed to overwrite and alter files **inline** without creating copies.

```bash
# Instantly scale all images in a folder to 50% scale, overwriting originals
mogrify -resize 50% *.jpg
```

#### `montage` (ImageMagick)

An ImageMagick tool used to tile separate individual images into a single combined grid composition.

```bash
# Combine 4 distinct photos into a clean 2x2 grid layout matrix
montage shot1.png shot2.png shot3.png shot4.png -geometry +2+2 grid.png
```

#### `cwebp` / `dwebp`

The official Google utilities for encoding images into the high-compression `.webp` format and decoding them back.

```bash
# Convert a heavy JPEG file into an optimized WebP image
cwebp -q 80 portrait.jpg -o portrait.webp

# Decompress a WebP file back into a standard PNG format
dwebp graphic.webp -o graphic.png
```

#### `yt-dlp`

A powerful command-line tool for downloading videos from YouTube, TikTok, Instagram, Twitch, and hundreds of other video platforms. It is a maintained fork of youtube-dl with regular updates and enhanced features.

```bash
# Download a video from YouTube in the best available quality
yt-dlp "https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# Download a video and extract audio as an MP3 file
yt-dlp -f bestaudio --audio-format mp3 "https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# Download a video playlist and organize files by video number
yt-dlp -o "%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s" "https://www.youtube.com/playlist?list=PLxxxxxx"

# Download at a specific resolution (1080p in this case)
yt-dlp -f "bestvideo[height<=1080]+bestaudio/best[height<=1080]" "https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# Download a video with subtitles and automatically add them to the media file
yt-dlp --write-subs --sub-langs en --embed-subs "https://www.youtube.com/watch?v=dQw4w9WgXcQ"

# Download all videos from a channel, limiting to the 50 most recent
yt-dlp -o "%(title)s.%(ext)s" --max-downloads 50 "https://www.youtube.com/@channelname/videos"

# Download a video and save with a custom filename template
yt-dlp -o "~/Downloads/%(title)s - %(uploader)s.%(ext)s" "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
```

---

### Version Control & Repositories (`git`, `gh`)

#### `git`

The distributed version control system for tracking source code changes.

```bash
# View a beautifully clean, colorized, single-line log of repository history
git log --oneline --graph --decorate --all

# Undo your last commit safely while keeping your edited changes staged
git reset --soft HEAD~1
```

#### `gh`

The official GitHub command-line workspace interface.

```bash
# Create a new private repository on GitHub directly out of your current folder
gh repo create my-new-project --private --source=. --remote=upstream

# Interactively view, review, and checkout a teammate's open pull request
gh pr checkout 42
```

### Network Diagnostics & Utilities

#### Classic vs. Modern Network Utilities Reference

A quick-reference comparison mapping legacy Linux `net-tools` and classic networking commands to their modern standard replacements (`iproute2`, `nftables`) and next-gen CLI tools (written in Rust, Go, and C).

| Legacy / Traditional Command | Modern Standard Replacement (`iproute2` / System) | Next-Gen CLI Alternative (Rust / Go / Modern) | Primary Use Case |
| :--- | :--- | :--- | :--- |
| `ifconfig` | `ip addr` / `ip link` | `nmcli`, `networkctl` | Network interface address & link state configuration |
| `route` | `ip route` | `nmcli route` | Displaying & modifying IP routing tables |
| `netstat` | `ss` | `lsof -i`, `ss -p` | Active socket monitoring & listening port inspection |
| `arp` | `ip neighbor` (`ip n`) | — | Address Resolution Protocol cache management |
| `iwconfig` | `iw` | `nmcli device wifi` | Wireless network interface & Wi-Fi configuration |
| `iptables` / `ip6tables` / `arptables` | `nftables` (`nft`) | `ufw`, `firewalld` | Packet filtering & stateful firewall rule management |
| `ifup` / `ifdown` | `ip link set dev <iface> up/down` | `nmcli device connect/disconnect` | Toggling network interface link states |
| `iptunnel` | `ip tunnel` | `wireguard` (`wg`) | IP tunneling & VPN encapsulation setup |
| `ipmaddr` | `ip maddr` | — | IP multicast address group management |
| `nameif` | `ip link set dev <iface> name <new>` | `udev` persistent naming | Renaming network interface device names |
| `mii-tool` | `ethtool` | — | NIC physical link status & hardware autonegotiation |
| `nslookup` / `host` | `dig`, `drill` | `doggo`, `dog`, `kdig` | DNS querying & domain record lookup |
| `ping` / `ping6` | `ping` | `gping`, `trippy` | ICMP reachability, latency & graphical pinging |
| `traceroute` / `tracepath` | `mtr` | `trippy`, `nexttrace` | Route tracing & intermediate hop loss analysis |
| `tcpdump` | `tshark` | `termshark` | Live packet analysis & pcap file dissection |
| `nc` (netcat) / `telnet` | `socat`, `ncat` | — | TCP/UDP socket relays, listeners & port testing |
| `curl` / `wget` | `curl`, `wget` | `httpie`, `curlie`, `xh` | HTTP requests, file downloads & REST API interaction |
| `nmap` | `nmap` | `rustscan`, `naabu` | Fast port scanning & host vulnerability auditing |
| `iftop` / `iptraf` / `bmon` | `nethogs` | `bandwhich` | Real-time interface & per-process bandwidth monitoring |
| `lsof -i` / `fuser` | `ss -p` | — | Socket process PID & open port ownership resolution |
| `whois` | `whois` | `rdap`, `ipinfo` | Domain metadata & IP geolocation WHOIS lookups |
| `stun` | `stunclient` / `stunserver` | `stuntman` | STUN protocol (RFC 5389/5780) NAT traversal & public IP discovery |

---

#### `ping` / `ping6`

Standard network diagnostic utility that uses ICMP Echo Request and Reply messages to test host reachability, measure round-trip delay (latency), detect packet loss, and analyze Path MTU constraints.

```bash
# Send 5 ICMP echo requests to a target host and exit
ping -c 5 8.8.8.8

# Send pings with a custom 200ms interval (-i) and custom payload size of 1000 bytes (-s)
ping -i 0.2 -s 1000 192.168.1.1

# Test Path Maximum Transmission Unit (MTU) by disabling packet fragmentation (DF bit)
ping -s 1472 -D 1.1.1.1

# Perform IPv6 ping connectivity check
ping6 -c 4 ipv6.google.com

# Play an audible ping on response (-a) with quiet summary output (-q)
ping -a -q -c 10 10.0.0.1
```

#### `traceroute` / `traceroute6` / `tracepath`

Traces the hop-by-hop network path packets take to reach a remote host by incrementally increasing the IP Time-To-Live (TTL) value, helping identify network latency bottlenecks and routing failures.

```bash
# Trace route to host without resolving IP addresses to hostnames for faster output
traceroute -n example.com

# Use ICMP Echo Request probes instead of default UDP probes
traceroute -I google.com

# Use TCP SYN packets targeted at port 443 to bypass firewalls blocking UDP/ICMP
traceroute -T -p 443 github.com

# Trace path while automatically discovering Path MTU (Maximum Transmission Unit)
tracepath -n 192.168.1.1

# Trace IPv6 route limiting maximum hops to 15
traceroute6 -m 15 ipv6.google.com
```

#### `mtr` (My TraceRoute)

Combines the capabilities of `traceroute` and `ping` into a single dynamic, real-time network diagnostic tool that continuously updates packet loss and latency statistics across all intermediate hops.

```bash
# Launch interactive real-time network monitoring interface
mtr 1.1.1.1

# Generate a non-interactive summary report based on 10 probe cycles
mtr --report --report-cycles=10 8.8.8.8

# Run MTR using TCP SYN probes targeting port 80 without resolving DNS hostnames
mtr -n -T -P 80 example.com

# Output raw data report suitable for automated parsing scripts
mtr --raw --report-cycles=5 192.168.1.1
```

#### `dig` (Domain Information Groper)

A flexible and powerful DNS lookup utility for querying DNS name servers for specific resource records (A, AAAA, MX, TXT, NS, CNAME, SOA) and troubleshooting DNS resolution paths.

```bash
# Query the IPv4 address (A record) for a domain with short output format
dig example.com A +short

# Query MX (Mail Exchanger) records specifically using Google DNS server (8.8.8.8)
dig @8.8.8.8 example.com MX

# Inspect SPF, DKIM, and domain ownership TXT records
dig example.com TXT

# Perform a reverse DNS lookup to find the domain associated with an IP address
dig -x 8.8.8.8

# Trace DNS resolution step-by-step from root servers down to authoritative servers
dig +trace example.com

# Query all available DNS records displaying only the answer section
dig example.com ANY +noall +answer
```

#### `nslookup`

An interactive and non-interactive command-line tool used to query DNS name servers and verify domain name or IP address mappings.

```bash
# Perform standard DNS lookup against default configured DNS server
nslookup example.com

# Query MX records for a domain using Cloudflare DNS at 1.1.1.1
nslookup -type=MX google.com 1.1.1.1

# Query all available DNS records for a host
nslookup -type=ANY github.com

# Perform reverse DNS lookup for an IP address
nslookup 1.1.1.1
```

#### `host`

A simple, concise DNS lookup utility that converts hostnames to IP addresses and vice versa with clean, scriptable output.

```bash
# Display IPv4 and IPv6 addresses associated with a domain
host google.com

# Query mail exchanger (MX) records for a domain
host -t MX github.com

# Retrieve TXT records for SPF or domain validation
host -t TXT example.com

# Display verbose DNS details including SOA records and TTL parameters
host -a example.com
```

#### `curl`

A foundational data transfer tool supporting HTTP, HTTPS, FTP, SFTP, and more. Essential for REST API testing, header inspection, file downloads, and connection timing benchmarks.

```bash
# Send an authenticated POST request with JSON payload and custom headers
curl -X POST https://api.example.com/v1/data \
     -H "Authorization: Bearer secret_token" \
     -H "Content-Type: application/json" \
     -d '{"status": "active"}'

# Fetch HTTP response headers only while following redirects (HEAD request)
curl -I -L https://example.com

# Download a remote file preserving its original remote filename
curl -O -L https://example.com/downloads/release.tar.gz

# Route request through a SOCKS5/HTTP proxy while skipping SSL certificate checks
curl -x http://proxy.local:8080 -k https://internal.dev

# Benchmark detailed HTTP connection latency breakdown (DNS, TCP, TLS, TTFB, Total)
curl -w "DNS: %{time_namelookup}s | Connect: %{time_connect}s | TLS: %{time_appconnect}s | TTFB: %{time_starttransfer}s | Total: %{time_total}s\n" -o /dev/null -s https://example.com

# Download large file with rate limiting (1 MB/s) and auto-resume capability (-C -)
curl --limit-rate 1M -C - -O https://example.com/large-archive.iso
```

#### `wget`

A non-interactive network file retriever engineered for reliable background downloads, recursive web mirroring, and automatic transfer resumption.

```bash
# Download a file directly to the current working directory
wget https://example.com/dataset.zip

# Resume an interrupted large file download
wget -c https://example.com/large-file.iso

# Recursively mirror a website section for offline viewing without parent traversal
wget --mirror --convert-links --page-requisites --no-parent https://example.com/docs/

# Download a list of URLs in background (-b) with rate limit cap of 500 KB/s
wget --limit-rate=500k -b -i urls.txt

# Download bypassing SSL certificate checks with custom User-Agent header
wget --user-agent="Mozilla/5.0" --no-check-certificate https://example.com/data.json
```

#### `nc` (Netcat) / `ncat`

The "Swiss Army Knife" of TCP/IP networking. Reads and writes data across network connections using TCP or UDP, supporting port scanning, listening servers, file transfers, and raw banner grabbing.

```bash
# Perform a fast TCP port scan checking ports 20 through 80 on a host
nc -zv 192.168.1.50 20-80

# Check if UDP port 53 (DNS) is open on target IP
nc -uzv 192.168.1.1 53

# Spin up a temporary listening server on port 8080 to monitor incoming traffic
nc -l 8080

# Transfer a file directly between two systems (Receiver: `nc -l 9000 > output.txt`)
nc 192.168.1.10 9000 < input.txt

# Manually construct and send a raw HTTP GET request to a web server
printf "GET / HTTP/1.1\r\nHost: example.com\r\nConnection: close\r\n\r\n" | nc example.com 80
```

#### `socat` (SOcket CAT)

A powerful multipurpose relay tool for bidirectional data transfer between two independent data streams (TCP, UDP, SSL/TLS, UNIX domain sockets, execution pipes, files).

```bash
# Set up a TCP port forwarder redirecting local port 8080 to a remote web server on port 80
socat TCP-LISTEN:8080,fork TCP:192.168.1.100:80

# Connect interactively to a network socket with readline history and editing support
socat READLINE TCP:192.168.1.1:23

# Expose a shell securely over an encrypted SSL/TLS socket connection
socat OPENSSL-LISTEN:443,cert=server.crt,key=server.key,verify=0 EXEC:/bin/bash

# Bridge a local UNIX domain socket to a TCP port socket
socat UNIX-LISTEN:/tmp/app.sock,fork TCP:127.0.0.1:3000
```

#### `nmap`

The premier open-source network exploration, port scanner, and vulnerability auditing utility. Identifies live hosts, open ports, service versions, operating systems, and security flaws.

```bash
# Perform a fast, stealthy TCP SYN scan on the top 1000 common ports
nmap -sS -p 1-1000 192.168.1.1

# Detect operating system details and running service versions on target ports
nmap -sV -O -p 22,80,443 target.com

# Perform aggressive scan (OS detection, version detection, script scanning, traceroute)
nmap -A 192.168.1.0/24

# Host discovery ping scan across a subnet without scanning individual ports
nmap -sn 192.168.1.0/24

# Run security vulnerability assessment scripts (NSE) against target host
nmap --script vuln target.com

# Execute HTTP header audit script saving output to a readable text file
nmap -p 80 --script http-headers target.com -oN scan_results.txt
```

#### `netstat`

A classic network monitoring tool for displaying active TCP/UDP connections, listening ports, kernel IP routing tables, interface statistics, and multicast memberships.

```bash
# List all listening TCP and UDP sockets with numerical IP addresses and port numbers
netstat -tuln

# List listening sockets with associated PIDs and process names (Linux)
netstat -tulnp

# Display all active network sockets with detailed process information (macOS)
netstat -anv

# Display kernel IP routing table with numerical addresses
netstat -rn

# Display summary network statistics broken down by protocol (IP, ICMP, TCP, UDP)
netstat -s

# Display network interface packet counters and error stats
netstat -i
```

#### `ss` (Socket Statistics)

A modern, high-speed replacement for `netstat` on Linux systems. Directly parses kernel netlink sockets to display socket states, TCP memory usage, and process associations.

```bash
# List all listening TCP and UDP sockets without resolving hostnames or port names
ss -tuln

# Show listening sockets along with process names and PIDs
ss -tulpn

# Display all active, established TCP connections
ss -t state established

# Filter established TCP connections targeting web ports (80 or 443)
ss -t state established '( dport = :https or dport = :http )'

# Display overall socket summary breakdown by protocol and connection state
ss -s

# View active TCP sockets accompanied by detailed socket memory allocation stats
ss -tm
```

#### `lsof` (List Open Files - Network Sockets)

Lists open files and active network sockets held by running processes. Indispensable for discovering which process is bound to a specific port or interface.

```bash
# Uncover which process PID is currently bound to port 8080
lsof -i :8080

# List all TCP sockets in LISTEN state with associated PIDs and user accounts
lsof -iTCP -sTCP:LISTEN

# Show all network connections owned by a specific user account
lsof -i -u www-data

# List all active connections established to or from a specific IP address
lsof -i @192.168.1.50

# List open UDP sockets without resolving hostnames or port service names
lsof -nP -iUDP
```

#### `ifconfig`

Classic interface configuration utility (macOS, BSD, Linux) used to display network interface parameters, assign IP addresses, toggle interface states, and adjust MTU settings.

```bash
# Display configuration and operating status for all active network interfaces
ifconfig

# Show detailed parameters for a specific network interface (e.g., en0)
ifconfig en0

# Temporarily disable and re-enable a network interface
sudo ifconfig en0 down
sudo ifconfig en0 up

# Assign a static IP address and netmask to a network interface
sudo ifconfig en0 inet 192.168.1.150 netmask 255.255.255.0

# Set Maximum Transmission Unit (MTU) size to 9000 bytes for Jumbo Frames
sudo ifconfig en0 mtu 9000
```

#### `ip` (iproute2 Suite - Linux Standard)

Modern Linux networking tool suite replacing `ifconfig`, `route`, and `arp`. Manages network interfaces, IP address assignments, routing tables, and neighbor ARP caches.

```bash
# Display IP addresses and netmasks assigned to all network interfaces
ip addr show

# Bring a network interface up or down
ip link set eth0 up
ip link set eth0 down

# Assign an IP address with CIDR netmask to an interface
ip addr add 192.168.1.50/24 dev eth0

# Display kernel IP routing table
ip route show

# Configure default gateway route for internet traffic forwarding
ip route add default via 192.168.1.1 dev eth0

# Display local ARP / neighbor cache table
ip neigh show
```

#### `route`

Displays and manipulates the IP routing table in kernel memory, defining static paths and default gateways for network packet forwarding.

```bash
# Print numerical IP routing table
route -n

# Add a static net route directing traffic for 10.0.0.0/8 through a specified gateway
sudo route add -net 10.0.0.0/8 gw 192.168.1.254

# Remove existing default gateway route
sudo route delete default

# Set new default gateway router address
sudo route add default 192.168.1.1
```

#### `arp` / `ip neighbor`

Displays and manages the Address Resolution Protocol (ARP) cache mapping IPv4 network addresses to physical MAC hardware addresses on local subnet segments.

```bash
# Display all active IPv4 to MAC address mappings in local ARP cache
arp -a

# Delete a specific IP entry from the ARP cache table
arp -d 192.168.1.50

# Manually add a static ARP entry binding an IP address to a MAC address
arp -s 192.168.1.10 00:11:22:33:44:55

# Modern Linux command to view neighbor ARP table
ip neighbor show
```

#### `tcpdump`

The command-line packet analyzer standard. Captures, filters, and records raw packet header and payload traffic on network interfaces for deep protocol debugging.

```bash
# Capture live network traffic on interface en0
sudo tcpdump -i en0

# Capture 100 packets without resolving IP addresses or port service names (-nn)
sudo tcpdump -i any -nn -c 100

# Filter traffic to capture HTTP and HTTPS packets only
sudo tcpdump -i eth0 port 80 or port 443

# Capture SSH traffic originating from a specific source host IP address
sudo tcpdump -i eth0 src host 192.168.1.50 and dst port 22

# Record captured packets directly to a raw `.pcap` file for Wireshark analysis
sudo tcpdump -i eth0 -w capture.pcap

# Read pcap file filtering exclusively for TCP SYN/ACK handshake packets
tcpdump -r capture.pcap -nn "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"
```

#### `tshark` (Wireshark CLI)

Terminal-based version of Wireshark. Offers advanced protocol dissection, display filtering, and field extraction directly from live interfaces or capture files without a GUI.

```bash
# Capture 50 packets on interface en0 displaying detailed protocol breakdown
tshark -i en0 -c 50

# Read pcap capture file applying Wireshark display filter for HTTP GET/POST requests
tshark -r capture.pcap -Y "http.request"

# Extract specific protocol fields (source IP, dest IP, HTTP host, URI) as tabbed values
tshark -r capture.pcap -T fields -e ip.src -e ip.dst -e http.host -e http.request.uri

# Extract TLS Server Name Indication (SNI) hostnames from encrypted client handshakes
tshark -r capture.pcap -Y "tls.handshake.type == 1" -T fields -e tls.handshake.extensions_server_name
```

#### `networkQuality` (macOS Native)

Built-in macOS command-line network benchmark tool that measures upload/download capacity alongside network responsiveness (RPM - Round-trips Per Minute under load).

```bash
# Run standard parallel upload/download throughput and latency benchmark test
networkQuality

# Execute parallel test checking both IPv4 and IPv6 network streams concurrently
networkQuality -p

# Display verbose real-time performance metrics during benchmark execution
networkQuality -v

# Run sequential download followed by upload test instead of simultaneous testing
networkQuality -s

# Output benchmark results formatted as machine-readable JSON data
networkQuality -j
```

#### `iperf3`

Point-to-point network bandwidth measurement tool. Generates customized TCP and UDP data streams between a server and client to test maximum throughput and packet loss.

```bash
# Launch iperf3 in listening server mode on default port 5201
iperf3 -s

# Run 30-second throughput test against server using 4 parallel TCP streams
iperf3 -c 192.168.1.100 -t 30 -P 4

# Run UDP bandwidth test targeting 100 Mbps rate to measure packet loss and jitter
iperf3 -c 192.168.1.100 -u -b 100M

# Run throughput test in reverse mode (measure download performance from server to client)
iperf3 -c 192.168.1.100 -R

# Export benchmark test results into a JSON output file
iperf3 -c 192.168.1.100 -J -o performance.json
```

#### `rsync`

Fast and versatile file synchronization and copying tool over local or SSH connections. Uses a delta-transfer algorithm to transfer only changed blocks of files.

```bash
# Synchronize local directory to remote server over SSH showing progress (-P)
rsync -avzP ~/Documents user@remote.server.com:/backup/Documents

# Mirror local directory to remote server, deleting remote files missing locally
rsync -avz --delete ~/Website/ user@remote.server.com:/var/www/html/

# Synchronize files using custom SSH key and alternate SSH port
rsync -avz -e "ssh -p 2222 -i ~/.ssh/deploy_key" ./dist/ user@remote.com:/app

# Limit bandwidth consumption to 1000 KB/s during synchronization
rsync -avz --bwlimit=1000 ~/large_folder/ /Volumes/Backup/
```

#### `ssh` / `scp` / `sftp`

Secure Shell network suite providing encrypted command-line logins, remote file copying, dynamic SOCKS proxying, and local/remote port tunneling.

```bash
# Connect to remote server using specific private SSH key and custom port
ssh -i ~/.ssh/id_ed25519 -p 2222 user@remote.host.com

# Local port forwarding: map local port 8080 to PostgreSQL (5432) on remote DB host
ssh -L 8080:localhost:5432 user@remote.db.com

# Create dynamic SOCKS5 proxy on local port 1080 without executing remote shell command
ssh -D 1080 -N user@remote.host.com

# Recursively copy local folder to remote destination via SCP on non-standard port
scp -P 2222 -r ./build user@remote.host.com:/var/www/

# Launch interactive SFTP session utilizing identity file authentication
sftp -i ~/.ssh/id_rsa user@remote.host.com
```

#### `whois`

Lookup utility for querying WHOIS protocol databases to fetch domain name registration metadata, registrar info, IP address range allocations, and ASN ownership details.

```bash
# Query domain WHOIS record for registration status, creation date, and nameservers
whois example.com

# Query IP address WHOIS record for netblock allocation and owner organization
whois 8.8.8.8

# Query specific regional WHOIS server for BGP routing information
whois -h whois.radb.net 1.1.1.1
```

#### `hping3`

Command-line oriented TCP/IP packet assembler and analyzer. Enables custom ICMP, UDP, and TCP packet crafting for firewall probing, port scanning, and stress testing.

```bash
# Send 4 TCP SYN packets targeted at port 80 to test firewall rule behavior
sudo hping3 -S -p 80 -c 4 target.com

# Perform ICMP traceroute with detailed header inspection
sudo hping3 --traceroute -V -1 target.com

# Probe target UDP port 53 to verify UDP service response
sudo hping3 -2 -p 53 -c 3 192.168.1.1

# Perform high-frequency TCP port probing to test SYN flood resilience
sudo hping3 -S -p 443 --fast 192.168.1.1
```

#### `ipcalc`

IPv4/IPv6 subnet calculator that takes IP addresses and netmasks or CIDR prefixes and calculates network, broadcast, wildcard masks, and host ranges.

```bash
# Calculate network address, broadcast, and host range for a /24 subnet
ipcalc 192.168.1.100/24

# Convert dotted decimal netmask to CIDR notation and show range parameters
ipcalc 10.0.0.0 255.255.240.0

# Output plain text calculation without color formatting or HTML markers
ipcalc -b 172.16.0.0/16
```

#### `speedtest-cli`

Command-line client for measuring internet bandwidth download speed, upload speed, and latency using Speedtest.net servers.

```bash
# Execute standard internet speed test against nearest server node
speedtest-cli

# Display simplified results showing only Ping, Download, and Upload speeds
speedtest-cli --simple

# Export speed test metrics as structured JSON payload
speedtest-cli --json

# List nearby Speedtest.net servers with server IDs
speedtest-cli --list

# Force speed test execution against a specific server ID
speedtest-cli --server 1234
```

#### `sniffnet`

Modern, cross-platform CLI tool for comfortably monitoring live network traffic intensity, bandwidth usage, and active application protocols in real-time.

```bash
# Launch interactive real-time traffic and protocol monitoring terminal interface
sniffnet
```

#### `iftop`

Real-time interface bandwidth monitor that displays bandwidth usage on a specific network interface broken down by communicating host pairs.

```bash
# Monitor real-time network traffic bandwidth on default interface
sudo iftop

# Monitor bandwidth usage specifically on interface en0
sudo iftop -i en0

# Disable DNS hostname resolution and port service lookup for faster real-time display
sudo iftop -n -N

# Filter monitoring display to HTTP and HTTPS web traffic only
sudo iftop -f "port 80 or port 443"
```

#### `nethogs`

Network monitoring utility that groups network bandwidth usage by process name and process ID (PID) rather than breaking down traffic per IP address.

```bash
# Monitor real-time network process bandwidth usage on default interface
sudo nethogs

# Monitor process bandwidth usage on specified interface en0
sudo nethogs en0

# Run in trace mode continuously appending bandwidth output for logging
sudo nethogs -t
```

#### `ethtool`

Linux kernel driver utility for querying and controlling network interface card (NIC) hardware parameters like link speed, duplex state, offloading features, and auto-negotiation.

```bash
# Display link status, speed, duplex mode, and supported auto-negotiation modes
ethtool eth0

# Force interface speed to 1000 Mbps full duplex with auto-negotiation disabled
sudo ethtool -s eth0 speed 1000 duplex full autoneg off

# Query hardware protocol offloading settings (e.g., TCP segmentation offload)
ethtool -k eth0

# Display low-level hardware statistics and physical packet error counters
ethtool -S eth0
```

#### `iw`

Modern Linux wireless network configuration tool replacing `iwconfig`. Controls Wi-Fi interfaces, scans access points, connects to SSIDs, and inspects wireless link quality.

```bash
# List all wireless devices and their capabilities
iw dev

# Scan for nearby Wi-Fi networks on interface wlan0
sudo iw dev wlan0 scan | grep SSID

# Display current wireless connection status and link quality
iw dev wlan0 link
```

#### `nftables` (`nft`)

Modern Linux packet filtering framework replacing `iptables`, `ip6tables`, and `arptables`. Features a unified syntax, higher throughput, and atomic rule updates.

```bash
# List current nftables ruleset layout
sudo nft list ruleset

# Create a filter table and add an input chain allowing HTTP, HTTPS, and SSH
sudo nft add table inet filter
sudo nft add chain inet filter input { type filter hook input priority 0 \; }
sudo nft add rule inet filter input tcp dport { 22, 80, 443 } accept

# Flush all active ruleset rules
sudo nft flush ruleset
```

#### `nmcli` / `networkctl`

Command-line utilities for NetworkManager (`nmcli`) and systemd-networkd (`networkctl`) to manage network devices, active connections, Wi-Fi networks, and routing.

```bash
# List all network interfaces and connection status
nmcli device status

# Connect to a Wi-Fi access point with passphrase
nmcli device wifi connect "SSID_NAME" password "WIFI_PASSWORD"

# Show systemd-networkd interface link states
networkctl list
```

#### `gping`

A modern ping utility that renders a real-time ASCII graph of latency directly inside your terminal, supporting concurrent pinging of multiple hosts for visual comparisons.

```bash
# Graph ping latency to Google DNS in real-time
gping 8.8.8.8

# Compare latency between multiple destinations simultaneously
gping 8.8.8.8 1.1.1.1 9.9.9.9
```

#### `trippy` (`trip`)

A next-generation, interactive network diagnostic TUI tool combining `ping`, `traceroute`, and `mtr` into a customizable interface with hop loss tracking and multipath tracing.

```bash
# Launch interactive TUI traceroute and ping matrix
trip 1.1.1.1

# Trace route using TCP SYN probes targeted at port 443
trip example.com -m tcp -p 443
```

#### `nexttrace`

An open-source, visual route tracking tool providing IP geolocation (country, city, ISP), Autonomous System Numbers (ASN), and BGP route details for each hop.

```bash
# Perform visual traceroute with IP geolocation breakdown
nexttrace 1.1.1.1

# Perform fast TCP-mode trace targeting port 80
nexttrace --tcp --port 80 example.com
```

#### `doggo` / `kdig` / `drill`

Modern DNS query clients designed as alternatives to `dig` and `nslookup`. Support colored output, JSON formatting, DNS-over-HTTPS (DoH), and DNS-over-TLS (DoT).

```bash
# Perform DNS lookup using Doggo with human-friendly output
doggo example.com

# Query DNS-over-HTTPS (DoH) using Cloudflare resolver outputting JSON
doggo example.com @https://cloudflare-dns.com/dns-query --json

# Query DNS records using Drill (from ldns suite)
drill example.com MX
```

#### `rustscan` / `naabu`

Ultra-fast modern port scanners designed to rapidly scan thousands of ports per second before piping open ports into `nmap` for detailed service inspection.

```bash
# Perform an ultra-fast scan of target IP, passing open ports directly to Nmap
rustscan -a 192.168.1.1 -- -sV -sC

# Fast host port discovery using Naabu (ProjectDiscovery)
naabu -host example.com -p 80,443,8080,8443
```

#### `bandwhich`

A terminal bandwidth utilization tool written in Rust that breaks down network usage by process name, remote socket connection, and target IP address.

```bash
# Monitor interface bandwidth categorized by processes and connections
sudo bandwhich

# Monitor bandwidth on specific interface without resolving DNS hostnames
sudo bandwhich -i en0 -n
```

#### `curlie` / `xh`

Modern HTTP clients designed as friendly cURL replacements. Combine cURL's raw speed and feature set with HTTPie's intuitive syntax and colorized, pretty-printed JSON output.

```bash
# Send GET request with colored JSON output using curlie
curlie GET https://api.github.com/users/octocat

# Send POST request passing JSON payload using xh
xh POST https://httpbin.org/post name="Jane Doe" role="admin"
```

#### `termshark`

A terminal user interface (TUI) for Wireshark (`tshark`), allowing terminal users to inspect pcap files and live captures using a pane-based interface similar to the Wireshark GUI.

```bash
# Open pcap file inside terminal UI viewer
termshark -r capture.pcap

# Capture live traffic on interface en0 inside terminal UI
termshark -i en0
```

#### `rdap` / `ipinfo`

Modern replacements for traditional WHOIS. Use Registration Data Access Protocol (RDAP) and REST APIs for structured JSON domain, IP address, and ASN geolocation lookups.

```bash
# Query domain registration metadata via RDAP protocol
rdap example.com

# Fetch IP address geolocation and ASN details using IPinfo CLI
ipinfo 8.8.8.8
```

#### `stuntman` (`stunclient` / `stunserver`)

An open-source STUN (Session Traversal Utilities for NAT) server and client implementation (RFC 5389, RFC 5780, RFC 3489). Used to discover public IP addresses, mapped ports, and NAT behavior (mapping & filtering types) for WebRTC, VoIP, and P2P applications.

```bash
# Query a public STUN server for your public IP address and mapped UDP port
stunclient stunserver.stunprotocol.org

# Perform a full RFC 5780 NAT behavior and filtering discovery test
stunclient --mode full stunserver.stunprotocol.org

# Send a STUN binding request to a specific port over TCP (default is UDP)
stunclient --protocol tcp stunserver.stunprotocol.org 3478

# Specify a custom local binding address and port for client requests
stunclient --localaddr 192.168.1.50 --localport 5000 stun.l.google.com 19302

# Force IPv6 mode for STUN server connectivity verification
stunclient --family 6 stunserver.stunprotocol.org

# Run a basic STUN server listening on default UDP port 3478
stunserver

# Start STUN server with verbose logging on a specific primary port
stunserver --primaryport 3478 --verbosity 1

# Run STUN server in full dual-interface mode for NAT behavior tests (RFC 5780)
stunserver --mode full --primaryinterface 192.168.1.10 --altinterface 192.168.1.11

# Start STUN server using settings loaded from a JSON configuration file
stunserver --configfile /etc/stuntman/stunserver.conf
```

---

### Text Processing & Modern CLI Utilities

#### Classic vs. Modern Text & CLI Utilities Reference

A quick-reference comparison mapping classic UNIX text manipulation, search, system monitoring, and shell navigation commands to their modern, high-performance CLI alternatives (written in Rust, Go, C, and modern C++).

| Classic / Traditional Command | Modern Standard / Popular Tool | Next-Gen CLI Alternative (Rust / Go / Modern) | Primary Use Case |
| :--- | :--- | :--- | :--- |
| `grep` | `ag` (The Silver Searcher), `ack` | `ripgrep` (`rg`) | Fast text & regex search across files |
| `cat` | `cat` | `bat` | File viewing with syntax highlighting & git integration |
| `head` / `tail` | `multitail` | `bat`, `hwatch` | File start/end inspection & live log watching |
| `less` / `more` | `less` | `bat`, `ov`, `moar` | Terminal pager with search & line wrapping |
| `sed` | `sed` | `sd`, `ast-grep` (`sg`) | Stream editing, string find/replace & AST refactoring |
| `awk` | `awk` | `miller` (`mlr`), `choose`, `fq` | Structured text processing, field extraction & binary query |
| `cut` | `cut` | `choose`, `tsv-utils` | Delimiter-based column & field slicing |
| `diff` | `diff` | `delta`, `difftastic` (`difft`) | File comparison, git diff syntax highlighting & AST diffing |
| `wc` | `wc` | `cw`, `tokei`, `scc` | Line, word, byte counting & source code metrics |
| `uniq` | `uniq` | `huniq` | Duplicate line filtering & high-speed hash-based deduplication |
| `sort` | `sort` | `miller` (`mlr`), `huniq` | Line ordering & structured data sorting |
| `tr` | `tr` | `sd` | Character translation & pattern replacement |
| `find` | `find` | `fd` | Recursive file directory searching |
| `hexdump` / `xxd` / `od` | `hexdump`, `xxd` | `hexyl` | Binary hex viewing with colorized byte breakdown |
| `jq` | `jq` | `jaq`, `fx`, `jless` | JSON processing, interactive navigation & query execution |
| `tree` | `tree` | `eza --tree`, `lsd --tree`, `tre` | Graphical directory tree structure display |
| `ls` | `ls` | `eza` (formerly `exa`), `lsd` | File & directory listing with icons, colors & git status |
| `du` | `du` | `dust` (`du-dust`), `ncdu` | Disk usage analysis & interactive visual disk profiling |
| `df` | `df` | `duf` | Disk filesystem space usage display with colorized graphs |
| `ps` | `ps` | `procs` | Process listing with colored columns, tree views & port lookups |
| `top` / `htop` | `htop` | `btop`, `bottom` (`btm`) | Real-time interactive CPU, GPU, memory & process monitoring |
| `man` | `man` | `tldr` (`tealdeer`), `cheat`, `navi` | Command manual pages, simplified examples & cheat sheets |
| `cd` | `cd` | `zoxide` (`z`), `autojump` (`j`) | Fast directory jumping using frecency-based fuzzy matching |

---

#### `grep` / `ripgrep` (`rg`) / `ag` / `ack`

Tools for searching regex patterns across single files or large codebase directories.

```bash
# Standard POSIX grep search across files recursively ignoring binary files
grep -rnI "error_code" /var/log/

# Ripgrep: Blazing fast search respecting .gitignore rules
rg "function processData" -g "*.js"

# Search exact word matches case-insensitively using Ripgrep
rg -i -w "todo"

# Search codebases using The Silver Searcher (ag)
ag --python "class User"

# Search JavaScript files using ack
ack --js "addEventListener"
```

#### `cat` / `bat`

Utilities for printing, concatenating, and viewing file contents in the terminal.

```bash
# Print file contents using standard cat
cat /etc/hosts

# View file with bat: syntax highlighting, line numbers, and git modifications
bat src/index.ts

# Plain output mode in bat without headers or decorations (cat replacement)
bat -p config.yaml

# Explicitly set syntax language for unlabelled or piped data
cat payload.json | bat -l json
```

#### `head` / `tail` / `multitail` / `hwatch`

Utilities for inspecting the beginning or end of files, watching live log streams, and monitoring command output changes.

```bash
# View the first 20 lines of a large file
head -n 20 server.log

# Monitor new incoming log lines in real-time
tail -f -n 50 /var/log/syslog

# Monitor multiple log files concurrently in split terminal windows using MultiTail
multitail /var/log/nginx/access.log /var/log/nginx/error.log

# Execute command repeatedly showing colored diffs of changes using hwatch
hwatch -n 1 "ls -la /tmp"
```

#### `less` / `more` / `ov` / `moar`

Terminal paging utilities that allow forward/backward navigation and searching through large text files or command outputs.

```bash
# Open large log file in less with line numbers (-N) and follow mode (+F)
less -N +F application.log

# Open file with ov pager featuring header pinning and column view
ov --header 1 data.tsv

# Open file with moar pager featuring automatic color retention and search
moar document.md
```

#### `sed` / `sd` / `ast-grep` (`sg`)

Stream editors and structural search/replace tools for string substitution and code AST refactoring.

```bash
# In-place regex substitution using standard sed
sed -i 's/http:\/\/localhost/https:\/\/api.example.com/g' config.env

# Intuitive regex search and replace using sd (Rust)
sd '(\d{4})-(\d{2})-(\d{2})' '$2/$3/$1' dates.txt

# Structural AST-based code search and rewrite using ast-grep (sg)
sg -p 'console.log($MSG)' -r 'logger.info($MSG)' --lang typescript
```

#### `awk` / `miller` (`mlr`) / `choose` / `fq`

Structured text parsing, field extraction, data formatting, and binary stream querying tools.

```bash
# Print 1st and 3rd columns from comma-delimited data using AWK
awk -F',' '{print $1, $3}' users.csv

# Process CSV data using Miller: filter rows and format output as JSON
mlr --csv --ojson filter '$age >= 21' data.csv

# Extract 1st and 3rd fields using human-friendly choose utility
choose 0 2 < input.txt

# Query and inspect binary file structures (MP4, PCAP, ELF, ZIP) using fq
fq . capture.pcap
```

#### `cut` / `tsv-utils`

Delimiter-based text slicing and tab-separated data processing tools.

```bash
# Extract the 1st and 5th fields from system passwd file using cut
cut -d':' -f1,5 /etc/passwd

# Filter and select specific columns from TSV data using tsv-utils
tsv-select -f 1,3,4 data.tsv
```

#### `diff` / `delta` / `difftastic` (`difft`)

File comparison utilities providing side-by-side diffs, syntax highlighting, and AST-aware structural code comparison.

```bash
# Standard unified diff between two files
diff -u old_version.py new_version.py

# View git diff with syntax highlighting and side-by-side views using delta
git diff | delta

# Perform structural AST code diff using Difftastic (understands syntax syntax, not just lines)
difft file_v1.js file_v2.js
```

#### `wc` / `cw` / `tokei` / `scc`

Word, line, character count tools and specialized source code metrics counters.

```bash
# Count total lines, words, and byte size of a file using wc
wc -l -w -c file.txt

# Count source code lines, comments, and blank lines by language using Tokei
tokei src/

# Fast code counter with complexity estimates using scc
scc .
```

#### `uniq` / `huniq`

Command-line utilities for filtering duplicate lines from text streams.

```bash
# Count occurrences of unique sorted lines using standard uniq
sort access.log | uniq -c | sort -nr

# High-speed hash-based deduplication without pre-sorting using huniq
cat massive_list.txt | huniq
```

#### `hexdump` / `xxd` / `od` / `hexyl`

Hexadecimal and binary data viewing utilities for inspecting raw byte offsets.

```bash
# Display binary file bytes in canonical hex and ASCII format
hexdump -C binary.bin

# Create hex dump using xxd (reversible back to binary with xxd -r)
xxd application.wasm

# Colorized command-line hex viewer with byte category highlighting using hexyl
hexyl --length 512 image.png
```

#### `jq` / `jaq` / `fx` / `jless`

JSON data processing, filtering, interactive terminal viewing, and query execution tools.

```bash
# Extract specific keys and filter arrays using jq
curl -s https://api.github.com/repos/cli/cli | jq '{name: .name, stars: .stargazers_count}'

# High-performance Rust alternative to jq (jaq)
cat data.json | jaq '.items[].id'

# Interactive JSON viewer and JS processing environment using fx
fx data.json

# Vim-like interactive JSON viewer with expanding/collapsing using jless
jless payload.json
```

#### `tree` / `eza --tree` / `lsd --tree` / `tre`

Graphical directory tree layout viewers displaying nested directory hierarchies.

```bash
# Print directory tree up to 2 levels deep ignoring git and node_modules
tree -L 2 -I 'node_modules|.git'

# Render directory tree with file icons and git status using eza
eza --tree --level=2 --icons

# Modern directory tree with automatic .gitignore filtering using tre
tre
```

#### `ls` / `eza` / `lsd`

File and directory listing utilities with colorization, file type icons, and git integration.

```bash
# Standard detailed file listing
ls -la

# Modern ls replacement (eza) with colorized metadata, icons, and git status
eza -la --git --icons --group-directories-first

# Next-gen ls command (lsd) featuring colorized grid layouts and file icons
lsd -la --header
```

#### `du` / `dust` (`du-dust`) / `ncdu`

Disk space usage estimation and interactive terminal disk profiling tools.

```bash
# Human-readable disk usage calculation using standard du
du -sh ~/Documents/*

# Graphical terminal disk usage tree representation using dust
dust

# Interactive ncurses-based disk usage analyzer (navigate and clean disk space)
ncdu /var/log
```

#### `df` / `duf`

Filesystem disk space usage tools showing mounted storage volumes and available capacities.

```bash
# Display mounted filesystems and human-readable capacity using df
df -h

# Modern colorful disk usage utility (duf) with clean table layouts
duf
```

#### `ps` / `procs`

Process monitoring and listing utilities displaying active system PIDs, resource usage, and tree hierarchies.

```bash
# Search for active process by name using standard ps
ps aux | grep node

# Modern process viewer (procs) with colored columns, tree view, and port lookups
procs node --tree
```

#### `top` / `htop` / `btop` / `bottom` (`btm`)

Real-time interactive system resource monitors tracking CPU, GPU, RAM, swap, processes, and disks.

```bash
# Interactive system monitor with mouse support and colorized meters (htop)
htop

# Modern, feature-rich TUI system monitor with graphs (btop)
btop

# Cross-platform graphical system monitor (bottom / btm)
btm
```

#### `man` / `tldr` (`tealdeer`) / `cheat` / `navi`

Documentation viewers, community-driven cheat sheets, and interactive command-line snippet lookup tools.

```bash
# Standard system manual page
man tar

# Practical, community-curated command examples using TLDR (tealdeer)
tldr tar

# View community cheat sheet for a command
cheat git

# Interactive command-line cheat sheet runner with auto-completion
navi
```

#### `cd` / `zoxide` (`z`) / `autojump` (`j`)

Directory navigation tools utilizing frecency algorithms to jump to frequently used folders instantly.

```bash
# Smart directory jump matching "proj" using Zoxide
z proj

# Interactive fuzzy search directory selection using Zoxide + fzf
zi

# Jump to folder matching "docs" using Autojump
j docs
```

---

### Archive & Compression Utilities

#### Classic vs. Modern Archive & Compression Utilities Reference

A quick-reference comparison mapping classic tape archiving, single-file compression, and archive extraction commands to their modern multi-threaded, high-ratio, and unified CLI replacements.

| Legacy / Traditional Command | Modern Standard / Parallel Tool | Next-Gen CLI Alternative (Rust / Go / Modern) | Primary Use Case |
| :--- | :--- | :--- | :--- |
| `tar` | `bsdtar`, `pigz` | `ouch`, `archiver` | Tape archive creation, extraction & parallel compression |
| `gzip` / `gunzip` | `pigz` (parallel gzip) | `zstd`, `ouch` | Standard single-file compression & decompression |
| `bzip2` / `bunzip2` | `pbzip2`, `lbzip2` | `zstd`, `bzip3` | High-ratio block-sorting file compression |
| `xz` / `unxz` / `lzma` | `pixz`, `pxz` | `zstd` | High-compression LZMA archive processing |
| `zip` / `unzip` | `7z` (7-Zip) | `ouch`, `dtrx` | Standard ZIP archive creation & extraction |
| `rar` / `unrar` | `unar` / `lsar` (The Unarchiver) | `7zz`, `ouch` | Proprietary RAR archive extraction & listing |
| `7z` / `p7zip` | `7zz` (official 7-Zip CLI) | `ouch` | Multi-format high compression ratio archiving |
| `zcat` / `gzcat` | `pigz -dc` | `zstdcat` | Direct viewing of compressed stream contents |
| `zgrep` / `zegrep` | `zgrep` | `ripgrep` (`rg -z`) | Searching regex patterns inside compressed archives |
| `zhead` / `zless` / `zmore` | `zless` | `ripgrep` (`rg -z`), `ov`, `moar` | Paging and inspecting compressed file streams |
| `compress` / `uncompress` (.Z) | `gzip` | `zstd` | Legacy LZW compression & modern decompression |
| `cpio` / `pax` | `bsdtar`, `pax` | `ouch` | POSIX interchange archive format handling |
| `lz4` | `lz4` | `zstd` | Ultra-fast real-time compression algorithm |
| `arc` / `arj` / `lha` | `unar`, `7z` | `ouch` | Legacy vintage archive format extraction |
| `dtrx` | `dtrx` | `ouch` (Obvious Unified Compression Helper) | Do-The-Right-Extract intelligent auto-extraction |
| `split` / `csplit` | `split` | `7zz` (volume split), `ouch` | File splitting & multi-volume archive creation |

---

#### `tar` / `bsdtar` / `archiver`

Standard tape archiving utilities used to bundle multiple files into a single `.tar` archive or compressed tarball (`.tar.gz`, `.tar.bz2`, `.tar.xz`, `.tar.zst`).

```bash
# Create a compressed tarball using gzip (-z) with verbose output (-v)
tar -czvf backup.tar.gz /var/www/app

# Extract a tarball into a specific target destination directory (-C)
tar -xzvf backup.tar.gz -C /opt/destination/

# Create a high-speed zstd-compressed tar archive using BSD tar
bsdtar -czvf archive.tar.zst --zstd ./data

# List contents of a tar archive without extracting (-t)
tar -tvf release.tar.xz
```

#### `pigz` (Parallel Gzip)

A parallel implementation of `gzip` that utilizes multiple CPU cores and threads to compress and decompress data at maximum hardware speed.

```bash
# Compress a large file using all available CPU cores
pigz large_database.sql

# Decompress a .gz file using parallel decompression threads
pigz -d large_database.sql.gz

# Pipe tar archive directly into pigz for fast multi-threaded tarball creation
tar -cf - ./project | pigz -9 > project.tar.gz

# Decompress and output to stdout (replacement for zcat / gzcat)
pigz -dc logs.tar.gz | head -n 100
```

#### `zstd` (Zstandard)

Facebook's real-time data compression algorithm providing high compression ratios and ultra-fast decompression speeds, outperforming gzip and xz.

```bash
# Compress a file using default zstd compression level (3)
zstd dataset.csv

# Compress with ultra-high compression level 19 (--ultra)
zstd -19 --ultra heavy_data.bin -o heavy_data.bin.zst

# Decompress a .zst compressed file
zstd -d dataset.csv.zst

# View uncompressed content directly to terminal (replacement for zcat)
zstdcat dataset.csv.zst
```

#### `pbzip2` / `lbzip2` / `bzip3`

Parallel implementations of `bzip2` using SMP systems to dramatically accelerate Bzip2 block-sorting compression and decompression.

```bash
# Compress file in parallel using pbzip2 with maximum compression (-9)
pbzip2 -9 large_file.tar

# Decompress .bz2 file in parallel using lbzip2
lbzip2 -d large_file.tar.bz2

# Compress using next-generation bzip3 block-sorting algorithm
bzip3 data.txt
```

#### `pixz` / `pxz` (Parallel XZ)

Parallel XZ compressors that split input data into independent blocks for multi-core XZ compression and indexed random-access extraction.

```bash
# Compress tar archive into parallel indexed XZ tarball
pixz backup.tar backup.tar.xz

# Decompress .xz file in parallel using all CPU threads
pxz -d archive.tar.xz

# Extract a single specific file from a pixz-indexed tarball instantly
pixz -x path/to/file.txt < backup.tar.xz | tar -x
```

#### `zip` / `unzip`

Traditional cross-platform archive compression tools for handling `.zip` format files.

```bash
# Create a password-protected encrypted zip archive (-e) recursively (-r)
zip -er -9 secret_files.zip ./confidential/

# Extract a zip archive silently (-q) into a target directory (-d)
unzip -q release.zip -d /var/www/html/

# Test the integrity of a zip file without extracting (-t)
unzip -t archive.zip
```

#### `unar` / `lsar` (The Unarchiver)

Modern command-line extraction tools capable of uncompressing almost any archive format (RAR, 7z, ZIP, TAR, ARJ, LHA, ISO) with robust encoding detection.

```bash
# List contents of an archive without extracting (lsar)
lsar archive.rar

# Extract an archive preserving non-ASCII filenames and automatic directory creation
unar archive.7z

# Extract a password-protected RAR or 7z file
unar -p "SECRET_PASSWORD" archive.rar
```

#### `7zz` (Official 7-Zip Standalone CLI)

The official standalone command-line version of 7-Zip. Offers highest compression ratios, multi-volume splitting, and support for 7z, ZIP, RAR, GZ, XZ, and ISO formats.

```bash
# Create a 7z archive with maximum LZMA2 compression level (-mx=9)
7zz a -mx=9 archive.7z ./my_folder/

# Extract archive with full directory path structure
7zz x archive.7z -o/target/directory/

# Test archive integrity
7zz t archive.7z

# List archive contents details (files, sizes, compression ratios)
7zz l archive.7z
```

#### `ouch` (Obvious Unified Compression Helper)

A modern CLI tool written in Rust that provides a single, painless syntax to compress and decompress files across any format (`.zip`, `.tar.gz`, `.tar.xz`, `.tar.zst`, `.7z`, `.rar`, `.bz2`).

```bash
# Decompress any archive format automatically based on file extension
ouch decompress archive.tar.zst

# Compress multiple files into a unified format transparently
ouch compress file1.txt folder2/ output.tar.gz

# List archive contents without extracting
ouch list archive.7z
```

#### `dtrx` (Do The Right Extract)

An intelligent extraction script that handles any archive file, automatically preventing nested directory "archive bombs" and creating clean extraction folders.

```bash
# Extract any archive cleanly into a dedicated folder without creating messy files
dtrx archive.tar.gz

# Recursively extract nested archives contained inside the target archive (-r)
dtrx -r archive.zip
```

#### `zcat` / `zstdcat` / `pigz -dc`

Stream viewing utilities for printing the uncompressed contents of compressed files directly to standard output without decompressing them on disk.

```bash
# Output contents of a gzipped file to terminal
zcat server_log.gz | grep "ERROR"

# Output contents of a zstd-compressed file to stdout
zstdcat metrics.json.zst | jq '.status'

# Fast parallel decompression stream output using pigz
pigz -dc heavy_log.gz | tail -n 50

#### Archive Regex Search (`ripgrep` `rg -z`)

Searching regex patterns directly inside compressed files (`.gz`, `.bz2`, `.xz`, `.zst`) without manually decompressing them first.

```bash
# Search for a pattern inside compressed logs transparently using ripgrep
rg -z "error" *.log.gz
```

---

### Forensic Tools

#### `exiftool`

A command-line tool for reading, writing, and editing meta information in a wide variety of file formats (EXIF, GPS, IPTC, XMP, JFIF, GeoTIFF, ICC Profile, Photoshop IRB, FlashPix, AFCP, and ID3).

```bash
# Extract all metadata from an image file
exiftool image.jpg

# Extract GPS data and display it in decimal degrees
exiftool -GPSLatitude -GPSLongitude -n image.jpg

# Change the creation date of a file (be careful with this!)
exiftool -CreateDate="2023:01:01 12:00:00" image.jpg
```

#### `tika` (Apache Tika)

A content detection and analysis framework that extracts text and metadata from over a thousand different file types (DOC, XLS, PPT, PDF, XML, HTML, etc.). It can be run as a standalone server or CLI tool.

```bash
# Extract text content from a PDF file
java -jar tika-app.jar -t document.pdf

# Extract metadata from a Word document
java -jar tika-app.jar -m document.docx

# Detect the file type of a given file
java -jar tika-app.jar -d unknown_file
```