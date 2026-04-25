# API Observation Notes

## Project
Restful-Booker

## Basic Endpoints Identified

### 1. Get all booking IDs
- Method: GET
- Path: /booking
- Purpose: Returns booking IDs and can support optional query filters

### 2. Get single booking
- Method: GET
- Path: /booking/:id
- Purpose: Returns one specific booking based on booking id

### 3. Health check
- Method: GET
- Path: /ping
- Purpose: Checks whether the API is up and running
