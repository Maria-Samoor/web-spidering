# Web Spidering

This Python script is designed to detect the web server technology of a given URL, crawl the website to discover internal URLs, and compare these URLs against a predefined list of default files. The results are saved in a text file for further analysis.

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Requirements](#requirements)
4. [Functions](#functions)
5. [Output](#output)

## Introduction

This script provides a comprehensive analysis of a website by:
- Detecting the web server technology.
- Crawling the website to discover internal URLs.
- Comparing discovered URLs against a list of default files.
- Generating a comparison matrix and saving the results.

## Features

- **Server Technology Detection**: Identifies the web server technology by analyzing the 'Server' header in the HTTP response.
- **Website Crawling**: Crawls the website to a specified depth to discover internal URLs.
- **Default File Comparison**: Compares discovered URLs against a predefined list of default files.
- **Hashing**: Computes SHA-256 hashes for URLs to ensure data integrity.
- **Results Saving**: Saves the results of the analysis in a text file.

## Requirements

- Python 3.x
- Libraries: `requests`, `bs4`, `pandas`, `hashlib`

## Functions

### `detect_technology(url)`
Detects the web server technology by analyzing the 'Server' header in the HTTP response.

### `get_default_file_path(server_header)`
Determines the default file list based on the detected server technology.

### `load_default_files(file_path)`
Loads the default file list from the given file.

### `hash_value(value)`
Computes the SHA-256 hash of a given value.

### `crawl_site(url, max_depth=3)`
Crawls a website to extract internal URLs up to a specified depth.

### `compare_urls(found_urls, default_files, base_url)`
Compares discovered URLs with the default file list.

### `create_cross_matrix(default_set, non_default_set, label1, label2)`
Generates a comparison matrix between default and non-default URLs.

### `save_results(default_found, non_default, url_matrix)`
Saves the results of the web scanning process to a file.

### `main()`
Main execution function to run the web scanning process.

## Output

The script generates a text file named `spidering_results.txt` containing:
- Default URLs found.
- Non-default URLs found.
- A cross-matrix comparison of URLs.
