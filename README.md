# Superset Extensions

A collection of community extensions for [Apache Superset](https://superset.apache.org/).

## Extensions

| Extension | Description |
|-----------|-------------|
| [sqllab_parquet](./sqllab_parquet) | Export SQL Lab query results to Apache Parquet format |

## Installation

Each extension includes its own installation instructions. Generally:

1. Install the Extensions CLI: `pip install apache-superset-extensions-cli`
2. Clone this repo and navigate to the extension folder
3. Run `superset-extensions bundle` to create the `.supx` bundle
4. Configure Superset to load the extension

See the [Superset Extensions Documentation](https://superset.apache.org/docs/developer_portal/extensions/overview) for more details.

## Contributing

Contributions welcome! Feel free to open issues or submit pull requests.

## License

Apache License 2.0
