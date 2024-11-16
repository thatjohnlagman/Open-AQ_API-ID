
# Modified Open AQ Data Retrieval with Station-Specific Targeting

## Description

Building on Jen Patrick Nataba's work, this repository features modified code to target specific air quality monitoring stations using location IDs from the Open AQ platform. By refining the dataset extraction process, this fork enables precise data retrieval for designated stations.

Additionally, this repository provides the CSV files containing the datasets pulled from these targeted stations.

## Features

- **Target Specific Stations**: Retrieve air quality data for specific monitoring stations using location IDs.
- **Data Transformation**: Process raw data into a structured, user-friendly format with pollutant-specific columns.
- **Export to CSV**: Save processed datasets for further analysis.
- **Enhanced Customization**: Supports location-specific data targeting for improved dataset accuracy.

## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/your-repository/enhanced-openaq-data-retrieval.git
    cd enhanced-openaq-data-retrieval
    ```

2. Install the required dependencies:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. Open the script `openaq_api.py` and configure the following variables:
    - `location_id`: ID of the monitoring station from the Open AQ platform.
    - `API_KEY`: Add your OpenAQ API key for authenticated requests.

2. Run the script:

    ```bash
    python openaq_api.py
    ```

The script will:
- Fetch air quality data for the specified station and date range.
- Process and save the dataset as `location_id_air_quality_data.csv`.

## Parameters and Customization

- **Station Targeting**: Update the `location_id` variable to fetch data for a specific monitoring station.
- **Pollutants**: Modify the `parameters` list to include or exclude specific pollutants.
- **Date Range**: Update the `start_date` and `end_date` variables in the `main()` function to fetch data for a custom time period.

## Example Output

The script generates a CSV file with columns for:
- Date (`date`)
- Location ID (`locationId`)
- Pollutant values (e.g., PM2.5, PM10, SO₂, etc.)
- Metadata such as city, country, latitude, and longitude.

## CSV Datasets

This repository also contains CSV files of datasets retrieved from targeted monitoring stations for further analysis.

## Limitations

- **API Rate Limits**: To respect OpenAQ's API rate limits, the script includes a 1-second delay between requests.
- **Data Availability**: Availability of pollutant data depends on OpenAQ's database for the specified location and time period.

## Dependencies

- **Python 3.x**
- Libraries: `requests`, `pandas`

Install dependencies using:

```bash
pip install requests pandas
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Original work by [Jen Patrick Nataba](https://github.com/jenpatricknataba).
- OpenAQ API for air quality data retrieval.
