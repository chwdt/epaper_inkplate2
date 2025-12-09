# Use the Inkplate2 ePaper display with esphome

Extraced as standalone external component from [arunderwood/esphome](https://github.com/arunderwood/esphome/tree/epaper-spi-inkplate2/esphome/components/epaper_spi)

```
external_components:
  - source: github://chwdt/epaper_inkplate2

spi:
  clk_pin: GPIO18
  mosi_pin: GPIO23

display:
  - platform: epaper_spi
    model: inkplate2
    cs_pin: GPIO27
    dc_pin: GPIO33
    reset_pin: GPIO19
    busy_pin: GPIO32
    rotation: 90
    lambda: |-
      // Clear to white background
      it.fill(COLOR_OFF);

      // Black circle on left
      it.filled_circle(70, 52, 30, COLOR_ON);

      // Red circle on right
      it.filled_circle(142, 52, 30, Color(255, 0, 0));
```
