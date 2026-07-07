# IoT Telemetry Data Standardizer
A Python module built as part of the Deloitte Australia Technology Job Simulation (via Forage), 
simulating a real-world consulting engagement for a client ("Daikibo") that needed telemetry 
data from multiple factory devices unified into a single, consistent format.

## Problem
Daikibo's IoT devices report telemetry in two different JSON schemas:
- **Format 1**: Flat structure with a slash-delimited location string (e.g. `"Australia/Melbourne/Area1/Factory1/Section1"`)
- **Format 2**: Nested structure with an ISO 8601 timestamp

## Solution
This script detects the incoming format and converts it into a unified schema containing:
- `deviceID`, `deviceType`, `timestamp` (epoch milliseconds)
- A structured `location` object (country, city, area, factory, section)
- A `data` object with device status and telemetry readings

## Testing
Includes a `unittest` suite validating both conversion paths against an expected output fixture, 
confirming correctness across formats.

## Tech
Python 3, `json`, `datetime`, `unittest`
