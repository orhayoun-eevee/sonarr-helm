# Sonarr Helm Chart

This Helm chart deploys Sonarr, a TV show collection manager, using the `app-chart` dependency pattern. The chart orchestrates application deployment, networking, and monitoring resources.

## Installation

```bash
helm install sonarr ./charts/services/sonarr-new --namespace media-center
```

## Configuration

See `values.yaml` for all available configuration options. The chart is organized into main sections:

- `app-chart`: Core application deployment configuration (Deployment, Services, PVC, etc.)
- `network`: Network access and security policies (HTTPRoute, NetworkPolicy)
- `metrics`: Monitoring, alerting, and dashboards (ServiceMonitor, PrometheusRule)

## Dependencies

This chart depends on:
- `app-chart` (v0.0.1) - Common application chart library

Before installing, ensure the dependency is available.

Update dependencies:
```bash
cd charts/services/sonarr-new
helm dependency update
```

## Key Differences from Radarr

- **User ID**: 1012 (vs Radarr's 1013)
- **Group ID**: 1011 (same as Radarr)
- **Media Path**: `/mnt/vol1/media-center/media/tv_shows` (vs movies)
- **Missing Items Metric**: `missing_episodes_total` (vs `missing_movies_total`)
- **Alert Names**: `SonarrCutoffUnmetHigh`, `SonarrMissingEpisodesHigh` (vs Radarr's movie alerts)
- **Exportarr Service Name**: "Sonarr" (vs "Radarr")

## References

- **Sonarr Documentation**: https://wiki.servarr.com/sonarr
- **Sonarr Environment Variables**: https://wiki.servarr.com/sonarr/environment-variables
- **Chart Dependencies**: See `Chart.yaml` for dependency versions
