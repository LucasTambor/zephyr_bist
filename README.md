# LP Core and BIST Example Application

This project demonstrates how to integrate the Zephyr OS on HP (High-Performance) and LP (Low-Power) cores of the ESP32-C6, along with the ESP-BIST library for built-in self-test functionality.

The first step is to initialize the workspace folder (``my-workspace``) where
the ``zephyr_bist`` and all Zephyr modules will be cloned. Run the following
command:

```sh
# initialize the workspace (main branch)
west init -m https://github.com/LucasTambor/zephyr_bist --mr main my-workspace
# update Zephyr modules
cd my-workspace
west update
```

## Building and running

To build the application, run the following command:

```sh
cd lpcore_bist
west build -p -b esp32c6_devkitc/esp32c6/hpcore app --sysbuild
```

Once you have built the application, run the following command to flash it:

```shell
west flash && west espressif monitor
```

## LP Core Console

Connect an UART to USB adapter to the LP Core's LP UART pins (TX: GPIO 5, RX: GPIO 4, GND: GND) and open a terminal emulator.
