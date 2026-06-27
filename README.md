# Morocco Real Estate — Scraping & EDA

Web scraping and exploratory data analysis project on the Moroccan real estate market.

## Overview

This project collects real estate listings data from Moroccan platforms, stores it, and performs exploratory analysis to understand pricing trends across cities and property types.

## Tech Stack

**Python** · **BeautifulSoup / Scrapy** · **Pandas** · **Jupyter Notebook** · **Docker**

## Project Structure

```
├── extract/            # Scraping scripts
├── staging/            # Raw data storage layer
├── clean/              # Cleaning and normalization scripts
├── data/               # Collected datasets
├── dockerfile          # Docker container config
├── docker-compose.yml  # Service orchestration
└── requirements.txt
```

## Pipeline

```
Web scraping → Staging (raw) → Clean (typed, normalized) → EDA
```

## How to Run

```bash
docker-compose up -d
python extract/scraper.py
python clean/clean.py
```
