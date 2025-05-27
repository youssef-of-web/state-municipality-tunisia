# Tunisian Governorate & Delegation Data

## Overview

A comprehensive dataset of Tunisia's administrative boundaries, including:

- **GeoJSON data** of Tunisia's administrative provinces/states with geographical boundaries
- **Structured JSON data** of Tunisian Governorates and their Delegations
- **Detailed locality information** including Arabic names, postal codes, and geographic coordinates (latitude/longitude)

This repository serves as a reference for developers, researchers, and anyone interested in Tunisia's administrative geography.

## Dataset Contents

This repository contains three main data files:

1. **tunisia_administrative_province_state_boundary.geojson**: GeoJSON file containing geographical boundary data for Tunisia's provinces/states.
2. **state-municipality.json**: Basic information about Tunisia's governorates and delegations.
3. **state-municipality-areas.json**: Expanded dataset with more detailed information about specific areas within delegations.

## Data Structure

### GeoJSON Boundary File
The GeoJSON file follows standard GeoJSON format with features representing each administrative province with their polygon boundaries.

### JSON Structure for Governorates and Delegations
*   **Governorate Level:**
    *   `Name`: English name of governorate
    *   `NameAr`: Arabic name of governorate
    *   `Value`: Identifier value
    *   `Delegations`: Array of Delegation objects

*   **Delegation Objects:**
    *   `Name`: English name (often with specific locality)
    *   `NameAr`: Arabic name
    *   `Value`: Identifier value
    *   `PostalCode`: Postal code
    *   `Latitude`: Geographical latitude
    *   `Longitude`: Geographical longitude

## Usage

This dataset can be used for:

- Building GIS applications focused on Tunisia
- Creating location-based services for Tunisian users
- Data visualization of administrative regions
- Research on urban planning and regional development
- Address validation and geocoding services

### Example Uses

```javascript
// Example of loading GeoJSON data for mapping
fetch('tunisia_administrative_province_state_boundary.geojson')
  .then(response => response.json())
  .then(data => {
    // Use data with mapping libraries like Leaflet or Mapbox
    // e.g., L.geoJSON(data).addTo(map);
  });

// Example of using governorate/delegation data
fetch('state-municipality.json')
  .then(response => response.json())
  .then(data => {
    // Filter or process administrative data
    const arianaGov = data.find(gov => gov.Name === "ARIANA");
    console.log(arianaGov.Delegations);
  });
```

## Purpose

This dataset is useful for:
- Location-based applications
- Geocoding services
- Administrative reference systems
- GIS and mapping projects
- Regional data analysis
- Urban planning initiatives

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
