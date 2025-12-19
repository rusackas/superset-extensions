# SQL Lab Parquet Export Extension

Export SQL Lab query results directly to Apache Parquet format with a single click.

![Export to Parquet](images/export-to-parquet.png)

## Features

- Export query results to Parquet with a single click
- Uses Snappy compression for optimal file size and performance
- Automatic filename generation with timestamp
- Handles various data types including dates and null values

## Installation

### Prerequisites

- Apache Superset with Extensions support
- Python packages: `pyarrow>=10.0.0`

### Using the Extensions CLI

```bash
# Install the CLI
pip install apache-superset-extensions-cli

# Clone this repo
git clone https://github.com/rusackas/superset-extensions.git
cd superset-extensions/sqllab_parquet

# Install dependencies and build
cd frontend && npm install && cd ..
superset-extensions bundle
```

This creates a `sqllab_parquet-1.0.0.supx` bundle.

### Configure Superset

Add the following to your `superset_config.py`:

```python
# Enable extensions feature
FEATURE_FLAGS = {"ENABLE_EXTENSIONS": True}

# For development (load from filesystem):
LOCAL_EXTENSIONS = ["/path/to/sqllab_parquet"]

# For production (load from bundled .supx files):
# EXTENSIONS_PATH = "/path/to/extensions/"
```

### Restart Superset

After configuration, restart your Superset instance for the extension to load.

## Usage

1. Open SQL Lab and write a query
2. Run the query to see results
3. Click the three-dot menu (**•••**) in the editor toolbar
4. Select **"Export to Parquet"**
5. The Parquet file will download automatically

## Why Parquet?

[Apache Parquet](https://parquet.apache.org/) is a columnar storage format that offers:

- **Efficient compression**: Snappy compression provides fast read/write with good compression ratios
- **Schema preservation**: Data types are preserved, unlike CSV
- **Wide compatibility**: Works with Spark, Pandas, DuckDB, and most data tools
- **Performance**: Columnar format enables efficient analytical queries

## License

Apache License 2.0
