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

#### `jq`

A lightweight and flexible command-line JSON processor. It lets you slice, filter, map, and transform structured JSON data with ease.

```bash
# Extract and pretty-print a specific key from a JSON payload
curl -s https://api.github.com/repos/stedolan/jq | jq '.description'

# Map an array of objects to filter out only specific fields
cat data.json | jq '[.[] | {name: .name, active: .status}]'
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

---

### Network Diagnostics & Transfer (`curl`, `nc`)

#### `curl`

A foundational data transfer tool utilized to hit endpoints and test networking.

```bash
# Send an authenticated POST request to an API passing header tokens
curl -X POST https://api.example.com/v1/data \
     -H "Authorization: Bearer secret_token" \
     -H "Content-Type: application/json" \
     -d '{"status": "active"}'
```

#### `nc` (Netcat)

The network networking utility ("Swiss army knife of TCP/IP") used to read and write data across network connections.

```bash
# Spin up a temporary listening server bound to port 8080 to monitor input traffic
nc -l 8080

# Perform a lightning-fast port scan checking TCP ports 20 through 80 on a host
nc -zv 192.168.1.15 20-80
```

---

### UNIX Core Utilities & File Management

#### `find`

The fundamental tool used to locate files and folders inside directory trees based on specialized conditions.

```bash
# Find and instantly delete all files ending in ".tmp" across your home folder
find ~ -type f -name "*.tmp" -delete

# Find files modified within the last 24 hours and list them detailed
find . -type f -mtime -1 -ls
```

#### `xargs`

A tool that reads items from standard input and constructs/executes command lines out of them.

```bash
# Safely pass a massive list of found logs into a file removal pipeline
find . -name "*.log" -print0 | xargs -0 rm

# Download a list of URLs contained inside a plain text file in parallel chunks
cat downloads.txt | xargs -n 1 -P 4 wget
```

#### `tar`

The standard tape archiving environment used to create, extract, and maintain system archive archives.

```bash
# Compress a target folder using maximum gzip extraction parameters
tar -czvf production_backup.tar.gz /var/www/app

# Extract a compressed archive block cleanly into an active path folder
tar -xzvf archive.tar.gz -C /target/directory/
```

#### `chown` / `chmod`

The baseline systems tools used to update operational user ownership and modification rights patterns.

```bash
# Change ownership of a folder and all its contents to a specific user and group
sudo chown -R www-data:www-data /var/www/html

# Adjust access permissions so only the owner can read/write a secure key file
chmod 600 ~/.ssh/id_rsa
```