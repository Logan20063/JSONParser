# JSONParser
A Python-based data ingestion tool that processes information from Google Sheets, Sendou.ink, and JSON files to populate a relational database using SQLAlchemy.

## Overview
After players register for tournaments through Google Sheets, compete on [Sendou.ink](https://sendou.ink), and submit their statistics, the JSON Parser consolidates the resulting data. It checks records across multiple sources and logs any discrepancies for manual review before inserting them into the database. The database then supplies data to the [Power BI visualizer](https://app.powerbi.com/view?r=eyJrIjoiNjBhZjA4NWItZDQ3MS00NDczLWIwNGYtOGM0ZTEyYzU4M2UxIiwidCI6IjMwNWUwZDUzLTVmYmEtNGNlMi05ZjdmLWNjNWVhZmRiODE4YSJ9&embedImagePlaceholder=true).

> **Note:** I did not develop the Power BI visualizer. My contributions focused on building and maintaining the data ingestion pipeline that supplies it.

## Features

### Replay Populator
Imports replay information from Google Sheets into the `ReplayTable` database table.

### Participant Populator
Populates participant and team-related database tables using two data sources:
- **Google Sheets:** `DimUniversity`, `DimTeam`
- **Sendou.ink:** `DimPlayer`, `Groupene`, `Participants`

### Stats Populator
Processes JSON data to populate match and statistical database tables:
- `DimPreparer`
- `DimMatch`
- `GameTable`
- `StatTable`

## Technologies
- Python
- SQLAlchemy
- SQLite
- MariaDB
- Sendou.ink API
- CSV Processing
- JSON Processing
