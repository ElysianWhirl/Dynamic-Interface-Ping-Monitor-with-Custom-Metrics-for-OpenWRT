# Dynamic-Interface-Ping-Monitor-with-Custom-Metrics-for-OpenWRT
This script continuously monitors multiple network interfaces on OpenWRT by pinging specific hosts assigned to each interface. It dynamically adjusts the routing metrics of each interface based on the success or failure of pings.

# Dynamic Interface Ping Monitor with Custom Metrics for OpenWRT

This script allows continuous monitoring of multiple network interfaces on an OpenWRT router by pinging different hosts assigned to each interface. It dynamically adjusts the routing metrics for each interface based on network stability (ping success or failure). The script is designed to help with automatic failover and recovery in a multi-interface setup.

## Features

- **Multi-interface monitoring**: Monitors several network interfaces like `usb0`, `usb1`, `eth1`, etc.
- **Custom hosts for each interface**: Each interface can ping a different host (e.g., 8.8.8.8, 1.1.1.1).
- **Automatic metric adjustment**: 
  - Increases metric (deprioritizes) if an interface fails to ping 3 times.
  - Resets the metric back to the default value after 3 consecutive successful pings.
- **Configurable intervals**: Set custom ping intervals between checks.

## Requirements

- **OpenWRT**: Ensure you are running this script on a system with OpenWRT installed.
- **UCI (Unified Configuration Interface)**: This script uses UCI to change routing metrics.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/dynamic-interface-ping-monitor.git
