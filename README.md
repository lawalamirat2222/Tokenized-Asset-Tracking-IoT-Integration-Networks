# Tokenized Asset Tracking IoT Integration Networks

A comprehensive blockchain-based system for tracking and monitoring physical assets using IoT sensors and smart contracts built on the Stacks blockchain using Clarity.

## Overview

This system provides a decentralized platform for:
- IoT provider verification and management
- Sensor integration with physical assets
- Real-time data collection from IoT devices
- Location tracking using GPS and positioning sensors
- Condition monitoring with automated alerts

## Architecture

### Smart Contracts

1. **IoT Provider Verification** (`iot-provider-verification.clar`)
    - Manages IoT service provider registration
    - Handles provider verification and reputation scoring
    - Controls provider status (pending, verified, suspended)

2. **Sensor Integration** (`sensor-integration.clar`)
    - Registers and manages IoT sensors
    - Links sensors to specific assets
    - Supports multiple sensor types (GPS, temperature, humidity, accelerometer)

3. **Data Collection** (`data-collection.clar`)
    - Collects sensor data from IoT devices
    - Stores historical and latest readings
    - Supports batch data submission

4. **Location Tracking** (`location-tracking.clar`)
    - Tracks asset locations using GPS coordinates
    - Maintains location history
    - Provides distance calculation utilities

5. **Condition Monitoring** (`condition-monitoring.clar`)
    - Monitors asset conditions based on sensor thresholds
    - Generates automated alerts for anomalies
    - Manages condition status (normal, warning, critical)

## Features

### Provider Management
- Secure provider registration process
- Reputation-based verification system
- Administrative controls for provider status

### Asset Tracking
- Real-time location monitoring
- Historical location data storage
- Multi-sensor support per asset

### Data Collection
- High-frequency data collection
- Quality scoring for sensor readings
- Batch processing capabilities

### Condition Monitoring
- Customizable threshold settings
- Automated alert generation
- Alert resolution tracking

## Getting Started

### Prerequisites
- Stacks blockchain development environment
- Clarity CLI tools
- Node.js for testing

### Installation

1. Clone the repository
2. Install dependencies for testing:
   \`\`\`bash
   npm install
   \`\`\`

3. Run tests:
   \`\`\`bash
   npm test
   \`\`\`

### Usage

#### Register an IoT Provider
\`\`\`clarity
(contract-call? .iot-provider-verification register-provider "IoT Solutions Inc")
\`\`\`

#### Register a Sensor
\`\`\`clarity
(contract-call? .sensor-integration register-sensor "SENSOR001" u1 u1 u100)
\`\`\`

#### Submit Sensor Data
\`\`\`clarity
(contract-call? .data-collection submit-data "SENSOR001" 2500 "celsius" u95 u1)
\`\`\`

#### Update Asset Location
\`\`\`clarity
(contract-call? .location-tracking update-location u100 400000000 -740000000 100 u5 u1 "GPS001")
\`\`\`

#### Set Condition Thresholds
\`\`\`clarity
(contract-call? .condition-monitoring set-threshold u100 u2 -1000 5000 500 1000)
\`\`\`

## Data Structures

### Provider Data
- Provider ID (unique identifier)
- Address (blockchain address)
- Name (provider company name)
- Status (pending/verified/suspended)
- Verification date
- Reputation score

### Sensor Data
- Sensor ID (unique identifier)
- Provider ID (linked provider)
- Sensor type (GPS, temperature, etc.)
- Asset ID (linked asset)
- Status (active/inactive)
- Installation and update timestamps

### Location Data
- Asset ID
- Coordinates (latitude, longitude, altitude)
- Timestamp
- Accuracy rating
- Provider and sensor information

### Condition Data
- Asset ID
- Overall status
- Individual condition statuses
- Alert information
- Threshold configurations

## Security Features

- Provider verification system
- Data quality scoring
- Access control mechanisms
- Immutable audit trail

## Testing

The system includes comprehensive tests using Vitest:
- Unit tests for each contract function
- Integration tests for cross-contract interactions
- Edge case and error condition testing

Run tests with:
\`\`\`bash
npm test
\`\`\`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions, please open an issue in the GitHub repository.
