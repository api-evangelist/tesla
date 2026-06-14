# Tesla GraphQL Schema

This directory contains a conceptual GraphQL schema for the Tesla Fleet API and Owner API. Tesla does not publish an official GraphQL endpoint, but this schema models the domain objects and operations available through their REST APIs as a GraphQL surface.

## Source APIs

- **Tesla Fleet API** — official partner API: https://developer.tesla.com/docs/fleet-api
- **Tesla Owner API** — community-documented: https://tesla-api.timdorr.com/

## Schema File

- `tesla-schema.graphql` — full GraphQL schema with 60+ named types

## Type Summary

### Auth / OAuth
| Type | Description |
|---|---|
| `Token` | Combined access + refresh token response |
| `AccessToken` | Scoped access token |
| `RefreshToken` | Long-lived refresh token |
| `OAuthClient` | Registered OAuth application client |
| `Application` | Developer application registration |

### Fleet / Vehicle List
| Type | Description |
|---|---|
| `VehicleList` | Paginated list of vehicles |
| `DataRequest` | Asynchronous telemetry data request |

### Vehicle Core
| Type | Description |
|---|---|
| `Vehicle` | Top-level vehicle resource with all sub-states |
| `VehicleConfig` | Static hardware/trim configuration |
| `VehicleState` | General vehicle state (doors, locks, odometer) |
| `SpeedLimitMode` | Speed limit mode settings |

### Drive State
| Type | Description |
|---|---|
| `DriveState` | GPS position, heading, speed, shift state |

### Charging
| Type | Description |
|---|---|
| `ChargingState` | Real-time charging data and battery levels |
| `ChargingSession` | Historical charging session record |
| `ChargingSchedule` | Scheduled charging configuration |
| `Supercharger` | Tesla Supercharger station |
| `NearbyCharger` | Nearby charger result from vehicle location |

### Climate
| Type | Description |
|---|---|
| `ClimateState` | HVAC settings, temperatures, seat heaters |
| `BioWeapons` | Bioweapon defense mode state |
| `FanSpeed` | Fan level and auto mode |

### Media
| Type | Description |
|---|---|
| `MediaState` | Remote control enabled, current playback |
| `MediaPlayback` | Now-playing track and playback position |
| `MediaQueue` | Ordered list of queued media items |
| `MediaItem` | Individual media track metadata |

### Software
| Type | Description |
|---|---|
| `SoftwareUpdate` | OTA firmware update status and progress |

### Vehicle Commands
| Type | Description |
|---|---|
| `VehicleCommand` | Result of a remote command sent to the vehicle |
| `WakeUp` | Wake-up request and resulting vehicle state |
| `MobileAccess` | Mobile access enable/disable state |
| `FleetAPI` | Fleet API metadata (version, rate limits) |

### Telemetry
| Type | Description |
|---|---|
| `TeleSync` | Streaming telemetry sync configuration |

### Navigation
| Type | Description |
|---|---|
| `NavStatus` | Active navigation route status |
| `NavRoute` | Full route from origin to destination |
| `RouteWaypoint` | Individual waypoint in a navigation route |

### Energy
| Type | Description |
|---|---|
| `EnergyHistory` | Historical energy production/consumption data |
| `EnergyDataPoint` | Single energy time-series data point |
| `EnergyLive` | Live Powerwall / solar energy readings |
| `EnergyEstimate` | Forecast energy estimates for a site |

### Alerts / Diagnostics
| Type | Description |
|---|---|
| `AlertLog` | Vehicle alert or notification record |
| `FaultCode` | OBD-style fault code from vehicle diagnostics |
| `DiagReport` | Full diagnostic report for a vehicle |
| `ServiceItem` | Individual service action within a diag report |

### Sentry Mode
| Type | Description |
|---|---|
| `Sentry` | Sentry mode status and storage usage |
| `SentryClip` | Recorded sentry video clip |
| `SentryEvent` | Triggering event for a sentry recording |

### Autopilot
| Type | Description |
|---|---|
| `Autopilot` | Autopilot availability and current state |
| `AutopilotState` | Active autopilot mode and following settings |
| `AutopilotAlert` | Autopilot attention/alert notification |

### Dashcam
| Type | Description |
|---|---|
| `DashcamClip` | Saved dashcam clip with download URL |

### Tire & Odometer
| Type | Description |
|---|---|
| `TirePressure` | Per-wheel tire pressure readings and warnings |
| `OdoReading` | Current odometer reading |

## Operations

### Queries (38)
Covering: vehicle lookup, all state sub-objects, charging sessions, schedules, nearby chargers, energy history/live/estimate, sentry clips, dashcam clips, alerts, fault codes, diagnostics, tire pressure, odometer, mobile access, telemetry, OAuth clients, and fleet API metadata.

### Mutations (38)
Covering: wake up, door lock/unlock, horn, lights, climate start/stop, bioweapon mode, fan speed, charge start/stop, charge limit, charge amps, charge schedule, charge port open/close, navigation, Supercharger routing, sentry mode, Homelink, trunk, mobile access, seat heaters, steering wheel heat, valet mode, speed limit, Summon, token refresh/revoke, and TeleSync start/stop.

### Subscriptions (9)
Real-time event streams for: vehicle state, drive state, charging state, climate state, software update, alert logs, sentry events, autopilot alerts, and energy live readings.

## References

- Tesla Fleet API Docs: https://developer.tesla.com/docs/fleet-api
- Tesla Fleet API Authentication: https://developer.tesla.com/docs/fleet-api/authentication/overview
- Community Owner API Reference: https://tesla-api.timdorr.com/
- TeslaPy Python SDK: https://github.com/tdorssers/TeslaPy
- Tesla API Ruby Gem: https://github.com/timdorr/tesla-api
- Tesla GitHub Organization: https://github.com/teslamotors
