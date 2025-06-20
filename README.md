# Trino Lance Connector

A Trino connector for reading and writing Lance format data. 
This connector allows Trino to query Lance datasets and fragments directly.

## Features

- **Lance Dataset Support**: Read data from Lance datasets
- **Lance Fragment Support**: Read data from individual Lance fragments
- **Schema Discovery**: Automatic schema detection from Lance metadata
- **Column Projection**: Efficient column selection and projection

## Building

To build the connector:

```bash
mvn clean package
```

## Installation

1. Build the connector using Maven
2. Copy the generated JAR file to your Trino plugins directory
3. Configure the connector in your Trino catalog properties

## Configuration

Create a catalog properties file (e.g., `etc/catalog/lance.properties`):

```properties
connector.name=lance
# Add any additional configuration properties here
```

## Usage

Once configured, you can query Lance data using SQL:

```sql
-- Query a Lance dataset
SELECT * FROM lance.default.my_dataset;

-- Query specific columns
SELECT id, name, value FROM lance.default.my_dataset WHERE value > 100;
```


## Development Guide

### Project Structure

Everything in this repository apart from the `plugin/trino-lance`
mimics the layout of the Trino project.
For example, the root pom file is a copy of the Trino root pom file with exactly the same content.
We periodically upgrade the Trino version to stay up to date with the latest Trino features.

### Build

Build project:

```shell
./mvnw install
```
