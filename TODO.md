# Sonarr Chart TODO

This document tracks items for the sonarr-new chart migration from umbrella chart pattern to app-chart pattern.

## Migration Status

- [x] Directory structure created
- [x] Chart.yaml created
- [x] Template files created
- [x] Dashboard JSON copied
- [ ] values.yaml fully migrated (needs conversion from umbrella to app-chart pattern)
- [ ] Chart.lock generated
- [ ] README.md completed
- [ ] Testing and validation

## Notes

This chart is being migrated from the umbrella chart pattern (application/networking/monitoring subcharts) to the app-chart dependency pattern (nested under app-chart dependency).
