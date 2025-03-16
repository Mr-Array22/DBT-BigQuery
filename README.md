# Sales Analytics dbt Project

A data transformation project built with dbt (data build tool) that processes sales data to create analytics-ready models for business intelligence and reporting.

## Project Overview

This project transforms raw sales data into structured, analytics-ready datasets using dbt. It implements a modern data modeling approach with staging and marts layers, along with custom macros for dynamic data partitioning.

### Key Features

- **Modular data modeling** with staging and marts layers
- **Dynamic data partitioning** for efficient query performance
- **Data validation tests** to ensure data quality
- **Optimized for BigQuery** as the data warehouse

## Project Structure

```
sales_analytics/
├── models/
│   ├── staging/           # Raw data transformations
│   │   └── stg_sales.sql  # Initial transformation of raw sales data
│   └── marts/             # Business-level aggregations
│       └── sales_final.sql # Final aggregated sales model
├── macros/
│   └── dynamic_partition.sql # Custom macro for data partitioning
├── tests/
│   └── sales_test.yml     # Data validation tests
├── dbt_project.yml        # Project configuration
└── README.md              # Project documentation
```

## Data Models

### Staging Models

- **stg_sales**: Transforms raw sales data from `sales-anayltics.sales_dataset.raw_sales` with basic cleaning and structure

### Marts Models

- **sales_final**: Aggregates sales data by country and product, calculating total orders and revenue with time-based partitioning

## Custom Macros

- **dynamic_partition**: Creates time-based partitions for efficient querying, separating recent data from historical data

## Getting Started

### Prerequisites

- dbt installed (version 1.0.0 or later)
- Access to a BigQuery instance
- Proper credentials configured in your dbt profile

### Installation

1. Clone this repository:
   ```
   git clone https://github.com/yourusername/sales_analytics.git
   cd sales_analytics
   ```

2. Install dbt dependencies:
   ```
   dbt deps
   ```

3. Configure your dbt profile in `~/.dbt/profiles.yml` with your BigQuery credentials

### Running the Project

Execute the following commands to build and test the models:

```bash
# Run all models
dbt run

# Run specific models
dbt run --select staging
dbt run --select marts

# Test all models
dbt test

# Generate documentation
dbt docs generate
dbt docs serve
```

## Data Lineage

Raw sales data → stg_sales → sales_final

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

[Your chosen license]

## Contact

[Your contact information]

### Resources:
- Learn more about dbt [in the docs](https://docs.getdbt.com/docs/introduction)
- Check out [Discourse](https://discourse.getdbt.com/) for commonly asked questions and answers
- Join the [chat](https://community.getdbt.com/) on Slack for live discussions and support
- Find [dbt events](https://events.getdbt.com) near you
- Check out [the blog](https://blog.getdbt.com/) for the latest news on dbt's development and best practices
