# VTEX Data Pipeline & Analytics Dashboard

## Overview

End-to-end data pipeline designed to extract operational and configuration data from VTEX APIs, store it in PostgreSQL, transform JSON responses directly in the database, and visualize insights through Power BI dashboards.

## Objective

Centralize logistics and operational data to monitor configurations, detect inconsistencies, and eliminate manual validation processes performed through the VTEX web interface.

## Architecture

VTEX API → Python Connector → PostgreSQL (ETL & Data Warehouse) → Power BI

## Data Sources

* Warehouses
* Docks
* Carriers
* Orders
* Order Details
* External Pickup Points

## Database Design

The PostgreSQL layer handles:

* Raw API storage
* JSON parsing and normalization
* Data validation rules
* Monitoring tables

Control tables implemented:

* load_log → tracks refresh history
* error_log → stores API/load errors
* sync_status → monitors API sync health

## Transformations

Performed directly in PostgreSQL:

* JSON field extraction
* Data normalization
* Duplicate detection
* Cross-validation (warehouses vs branches)
* Status validation for active/inactive entities

## Dashboards

Power BI dashboards designed for operational monitoring:

* Logistics configuration overview
* Warehouse status tracker
* Order performance metrics
* Data sync monitoring panel

## Current Status

Project in active development.
Complementary datasets currently being integrated:

* Branches table
* Ubigeos table
* External pickup point data

## Business Value

* Reduces manual configuration audits
* Detects outdated or test configurations
* Centralizes operational visibility
* Enables faster decision-making

## Tech Stack

* PostgreSQL
* Python
* Power BI
* SQL
* REST APIs

## Author

Gerardo Espinoza
Industrial Engineer — Data & BI Specialist
Lima, Peru
Open to opportunities | Freelance projects

