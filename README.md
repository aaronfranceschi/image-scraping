# Web Scraper & Image Downloader

A robust, extensible Python project designed for concurrent web scraping and batch image downloading. This repository contains a comprehensive, production-ready implementation with retry logic, per-host rate-limiting, concurrent downloads, and detailed reporting capabilities.

## Features

- CSV-based input processing (local or remote sources)
- Web page scraping with automatic link extraction
- Concurrent downloads with configurable worker threads
- Automatic retry mechanism for failed downloads
- Per-host rate-limiting to respect server resources
- Detailed CSV reporting of results and errors
- Resumable downloads with temporary file handling

## Requirements

- Python 3.8+
- Dependencies listed in `requirements.txt`

## Installation

1. Create and activate a virtual environment:

```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Usage

Run the scraper with your data source:

```bash
python main.py --csv data.csv --out downloads --workers 8 --max 500 --delay 1.0 --report results.csv
```

### Common Options

- `--csv`: Path or URL to CSV input file
- `--out`: Output directory for downloaded files
- `--workers`: Number of concurrent download threads
- `--max`: Maximum number of items to process
- `--delay`: Minimum seconds between requests to same host
- `--report`: Output CSV file for results summary

## Project Structure

- [downloader.py](downloader.py): Core scraping and download logic
- [main.py](main.py): Command-line interface
- [rate_limiter.py](rate_limiter.py): Per-host rate limiting
- [reporter.py](reporter.py): Results reporting
- [requirements.txt](requirements.txt): Python dependencies

## Best Practices

- Use appropriate `--delay` values to avoid overwhelming target servers
- Start with small `--max` values for testing
- Respect `robots.txt` and terms of service
- Adjust worker count based on your system resources
- Review the generated report for any issues

