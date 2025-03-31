# ble_wifi_beacon

# Sample functionality

Combined build for Wi-Fi and BLE 

- Wi-Fi in Raw tx mode (non-connected mode)

  - Transmitting two beacons each with 51ms interval with unique SSID & BSSID to emulate two APs (AP1 and AP2) beaconing at ~102ms (timing is configurable)

  - All parameters like beacon transmission frequency, data rate, payload/length, channel etc are configurable as usual

- BLE

  - Configured as a peripheral in Advertising mode (scannable but not connectable)

  - Transmits continuous adv packets#

# Building

Install NCS v2.9.1, put the repository folder under ncs\nrf\samples\wifi and build as it an normal sample.


## Build commands

...
nRF54L15 + nRF7002eb2 - west build -p -b nrf54l15dk/nrf54l15/cpuapp -- -Dble_rawtx_SHIELD=nrf7002eb2 -Dble_rawtx_SNIPPET=nrf70-wifi -DCONFIG_RAW_TX_PKT_SAMPLE_NON_CONNECTED_MODE=y -DCONFIG_RAW_TX_PKT_SAMPLE_TX_MODE_CONTINUOUS=y -DCONFIG_RAW_TX_PKT_SAMPLE_INTER_FRAME_DELAY_MS=51
...

...
nRF7002 DK - west build -b nrf7002dk/nrf5340/cpuapp -- -DCONFIG_RAW_TX_PKT_SAMPLE_NON_CONNECTED_MODE=y -DCONFIG_RAW_TX_PKT_SAMPLE_TX_MODE_CONTINUOUS=y -DCONFIG_RAW_TX_PKT_SAMPLE_INTER_FRAME_DELAY_MS=51
...

# Modify Wi-Fi beacon MAC addresses


