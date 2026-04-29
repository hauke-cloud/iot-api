# IoT API

This repository contains shared API definitions for the hauke.cloud IoT platform.

## Packages

### alerts

The `alerts` package provides type definitions for the IoT Alert Service API. These types are used by services that handle device alert thresholds and notifications.

**Types:**
- `AlertDevice` - Represents a device that has triggered an alert threshold
- `AlertConditionInfo` - Contains information about the alert condition
- `AlertsResponse` - Response format for the alerts endpoint
- `AlertFilters` - Filter parameters for alert queries
- `ErrorResponse` - Standard error response format

## Usage

Import the package in your Go module:

```go
import "github.com/hauke-cloud/iot-api/alerts"
```

Add the dependency to your `go.mod`:

```
require github.com/hauke-cloud/iot-api v0.0.1
```

## License

Apache License 2.0
