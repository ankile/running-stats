# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Deprecation Notice

This project is deprecated. The [run-track](../run-track/) project supersedes this one with Garmin integration and more features. Use that project instead.

## Project Overview

This is a personal training data analysis project that processes running/exercise data from JSON training session files and creates visualizations for trend analysis. The project consists of two main Jupyter notebooks that handle data processing and visualization.

## Key Dependencies

The project uses Python with Jupyter notebooks. Key libraries include:
- pandas for data manipulation
- matplotlib for plotting 
- numpy for numerical operations
- tqdm for progress bars
- pathlib for file handling

Install dependencies with:
```bash
pip install -r requirements.txt
```

## Data Pipeline

1. **Raw Data**: JSON files in `data/raw/` containing training session data with exercise records
2. **Processing**: `process_raw_data.ipynb` extracts running data (RUNNING, TREADMILL_RUNNING sports) and converts to CSV
3. **Analysis**: `plot_trends.ipynb` creates weekly/monthly distance trend charts with event markers for races
4. **Output**: Processed data saved to `data/processed/running_data.csv`

## Key Files

- `process_raw_data.ipynb`: Data extraction and cleaning from raw JSON training sessions
- `plot_trends.ipynb`: Trend visualization with race event markers and goal tracking
- `data/processed/running_data.csv`: Clean dataset with date_and_time, distance (km), duration (seconds)

## Data Structure

The processed CSV contains:
- `date_and_time`: Timestamp of training session
- `distance`: Distance in kilometers (converted from meters)
- `duration`: Duration in seconds (converted from ISO 8601 format)

## Visualization Features

The trend charts include:
- Weekly and monthly distance aggregations
- Average and goal line overlays (25km/week, 100km/month goals)
- Race event markers with angled labels for major marathons/half-marathons
- Grid and formatted date axes for readability