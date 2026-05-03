# Tesla

Tesla, Inc. is an American electric vehicle and clean energy company. Tesla offers the Fleet API for partners to access Tesla vehicles and energy devices with owner-granted permissions, covering vehicle telemetry, remote commands, charging management, energy site management, and fleet management capabilities.

**Type:** Company  
**Developer Portal:** https://developer.tesla.com  
**Website:** https://www.tesla.com  
**GitHub:** https://github.com/teslamotors  

## APIs

### Tesla Fleet API
The official Tesla partner API providing access to Tesla vehicles and energy devices with OAuth permissions. Supports vehicle telemetry, remote commands, charging, and energy site management.

- **Base URL:** `https://fleet-api.prd.na.vn.cloud.tesla.com/api/1`
- **Authentication:** OAuth2 Bearer token
- **Documentation:** https://developer.tesla.com/docs/fleet-api

### Tesla Owner API
Community-documented access to Tesla vehicles via the owner-api.teslamotors.com endpoint.

- **Base URL:** `https://owner-api.teslamotors.com/api/1`
- **Authentication:** Bearer token
- **Documentation:** https://tesla-api.timdorr.com/
- **OpenAPI Spec:** [openapi/tesla-openapi-original.yml](openapi/tesla-openapi-original.yml)

## Artifacts

| Type | Files |
|------|-------|
| OpenAPI Specs | [openapi/](openapi/) |
| Spectral Rules | [rules/tesla-rules.yml](rules/tesla-rules.yml) |
| Capabilities | [capabilities/](capabilities/) |
| JSON Schema | [json-schema/](json-schema/) |
| JSON Structure | [json-structure/](json-structure/) |
| JSON-LD | [json-ld/tesla-context.jsonld](json-ld/tesla-context.jsonld) |
| Examples | [examples/](examples/) |
| Vocabulary | [vocabulary/tesla-vocabulary.yml](vocabulary/tesla-vocabulary.yml) |

## Capabilities

### Workflow Capabilities
- **[vehicle-monitoring.yaml](capabilities/vehicle-monitoring.yaml)** — Tesla vehicle telemetry monitoring and remote control (15 tools)

### Shared Per-API Definitions
- **[shared/tesla.yaml](capabilities/shared/tesla.yaml)** — Tesla Owner API: vehicle listing, telemetry, and remote commands (14 tools)

## Tags

Automobiles, Cars, Vehicles, Electric Vehicles, Energy, Clean Energy, IoT, Tesla, Remote Commands, Telemetry

## Maintainers

**FN:** Kin Lane  
**Email:** kin@apievangelist.com
