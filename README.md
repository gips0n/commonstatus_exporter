# commonstatus_exporter
Prometheus CommonStatus blackbox exporter

## Configuration

To configure exporter use environment variables:
* COMMONSTATUS_EXPORTER_LOG_LEVEL - set log level, supported values: DEBUG, INFO, WARN, ERROR; default: INFO
* COMMONSTATUS_CONNECTION_TIMEOUT - set connection timeout; default: 8 seconds
* COMMONSTATUS_EXPORTER_PORT - set port on which the exporter will run; default: 9259

### Connection timeout

Connection timeout occurs when the exporter sends requests to backends (from which it scapes metrics). The value is controlled by:

1. "X-Prometheus-Scrape-Timeout-Seconds" header in probe-request - per probe, has the highest priority, configured on prometheus server side
2. COMMONSTATUS_CONNECTION_TIMEOUT environment variable - default for all probes
3. Default value of COMMONSTATUS_CONNECTION_TIMEOUT - default for all probes
