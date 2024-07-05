# Custom 5x7 Dactyl Manuform with Integrated Trackball

![dactyl manuform keyboard](https://github.com/trentrand/zmk-config/blob/main/images/keyboard.jpeg?raw=true)

## Description

This is a custom-built 5x7 Dactyl Manuform keyboard, generated using the Cosmos Dactyl Generator. It features an integrated trackball, combining ergonomic split keyboard design with convenient pointer control.

## Software

This keyboard runs on ZMK Firmware, a modern, open-source keyboard firmware built on the Zephyr RTOS.

Firmware is compiled in CI with GitHub Actions.

### Custom ZMK Branch

The keyboard utilizes a custom ZMK branch by [petejohanson/feat/pointers-move-scroll](https://github.com/petejohanson/zmk/tree/feat/pointers-move-scroll). This branch implements mouse pointer functionality, which is crucial for the trackball operation. While this is currently an unmerged branch, it's commonly referenced in the ZMK community for pointer implementations.

**Note:** This branch is expected to be merged into the main ZMK repository in the future.

### Custom PMW3610 Driver

To enable the trackball functionality, this build incorporates a custom Zephyr driver for the PMW3610 sensor. The driver is implemented by [inorichi](https://github.com/inorichi/zmk-pmw3610-driver).

## Hardware

### Trackball Integration

The trackball uses a PMW3610 sensor, which is mounted on a custom breakout board. The PCB design for this breakout board was sourced from the [siderakb/pmw3610-pcb](https://github.com/siderakb/pmw3610-pcb) repository.

Fabrication Process:

1. PCB design files were obtained from siderakb's repository.
2. The PCB was ordered from an Electronic Design Automation (EDA) service.
3. The PMW3610 module was sourced separately and soldered onto the fabricated PCB.

Special thanks to siderakb for providing the open-source PCB design files.

### Build Process

#### Components Used

- PLA filament for 3D printed enclosure
- SuperMini nRF52840 Pro Micro Bluetooth LE microcontroller
- 3.7v 2600mAh batteries
- Kailh Hot-swap Sockets
- 28 AWG Enameled Copper Wire
- 1N4148 schottky switching diode
- Gateron Mini i switches
- Keycaps
- PMW3610 optical mouse sensor ([Product Details](https://www.pixart.com/products-detail/21/PMW3610DM-SUDU))
- 1.34 inch trackball
- 304 stainless steel dowel pin
- MR63ZZ mini ball bearings 3x6x2.5mm

#### Assembly Steps

1. Enclosure Preparation:

- Generate the keyboard design using the Cosmos Dactyl Generator.
- 3D print the enclosures using PLA filament.

2. Switch Socket Installation:

- Insert Kailh hot-swap sockets into the designated positions in the 3D printed enclosure.

3. Wiring:

- Solder columns using 28 AWG enameled copper wire.
- Solder rows using 1N4148 shottky siwtching diodes.
- Attach Dupont connectors to the end of each row and column.

4. Microcontroller Connection:

- Connect the row and column wires to the nRF52840 microcontroller.
- Attach the PMW3610 breakout board for the trackball.
- Connect the necessary wiring from the PMW3610 to the nRF52840 microcontroller.

5. Trackball Assembly:

- Install the 1.34 inch trackball.
- Use the 304 stainless steel dowel pin and MR63ZZ mini ball bearings for smooth trackball operation.

6. Switch and Keycap Installation:

- Insert Gateron Mini i switches into the hot-swap sockets.
- Place the keycaps onto the switches.

7. Power Supply:

- Connect the 3.7v 2600mAh batteries to power the keyboard.
- Attach the batteries to the enclosure using adhesive.

8. Firmware and Configuration:

- Program the keymap and ZMK configuration onto the nRF52840 microcontroller.
- Implement the custom PMW3610 driver for trackball functionality.

**Notes**

- The build process requires careful attention to detail, especially during the wiring phase. Test one side before proceeding to the other.
- Enamel wire is recommended for wiring due to the ability to melt the enamel coating at solder points.

![left keyboard wiring](https://github.com/trentrand/zmk-config/blob/main/images/wiring-left.jpeg?raw=true)
![right keyboard wiring](https://github.com/trentrand/zmk-config/blob/main/images/wiring-right.jpeg?raw=true)

## Acknowledgements

- [rianadon for the Cosmos Dactyl Generator](https://github.com/rianadon/dactyl-configurator)
- [inorichi for the PMW3610 driver](https://github.com/inorichi/zmk-pmw3610-driver)
- [siderakb for the PMW3610 breakout board PCB design](https://github.com/siderakb/pmw3610-pcb)
- [petejohanson for the custom ZMK branch with pointer implementation](https://github.com/petejohanson/zmk/tree/feat/pointers-move-scroll)
- [petejohanson and the open source community for the ZMK Firmware](https://github.com/zmkfirmware/zmk)
