# Restaurant GIS Map

An interactive web map that displays restaurant locations using data retrieved from a PostgreSQL database through the Supabase REST API.

This project is part of my exploration of GIS development and web-based mapping.

## Features

- Interactive map using Leaflet
- OpenStreetMap base map
- Restaurant data stored in PostgreSQL with Supabase
- Restaurant data retrieved using the Supabase REST API
- Dynamic map markers generated from latitude and longitude stored in the database
- Restaurant information displayed in marker popups
- Row Level Security (RLS) configured for read-only public access
- Map automatically adjusts to display returned restaurant locations

## Technologies

- HTML
- CSS
- JavaScript
- Leaflet
- OpenStreetMap
- Supabase
- PostgreSQL
- REST API

## How It Works

Restaurant information is stored in a PostgreSQL database hosted by Supabase.

The browser requests restaurant data from the Supabase REST API:

```text
PostgreSQL
    ↓
Supabase REST API
    ↓
JavaScript Fetch API
    ↓
Leaflet
    ↓
Interactive Map
```

Each restaurant record contains information such as:

```text
name
latitude
longitude
cuisine
rating
price_level
outdoor_seating
```

JavaScript retrieves the records and uses the latitude and longitude values to dynamically create Leaflet markers.

## Security

Supabase Row Level Security (RLS) is enabled on the restaurant table.

Anonymous users have read-only (`SELECT`) access to restaurant data. Public users are not granted permission to insert, update, or delete records.

The frontend uses a Supabase publishable key. No secret or service-role keys should be committed to this repository.

## Future Improvements

As I continue learning geospatial development, I plan to expand this project with features such as:

- Restaurant filtering
- Custom map markers
- PostGIS
- Spatial queries
- Distance-based searches
- GeoJSON
- QGIS integration

## Purpose

The goal of this project is to explore how traditional web development technologies can be combined with GIS tools and spatial databases to build data-driven mapping applications.