# I2C LCD Driver for ESP32

This repository contains a simple I2C LCD driver for ESP32 microcontrollers written in C. The driver allows interfacing with I2C-enabled LCD screens using the ESP-IDF framework.
Prerequisites

Before using this driver, ensure you have the ESP-IDF development environment set up on your system. You can find instructions on setting up the ESP-IDF framework here.
Hardware Setup

Connect your I2C-enabled LCD screen to the ESP32 using the specified GPIO pins in the lcd_pins_t structure. Make sure to adjust the pin configuration according to your hardware setup.
## Installation

Clone this repository to your local machine:

``` git clone https://github.com/yourusername/esp32-i2c-lcd-driver.git ```

Navigate to the project directory:

```cd esp32-i2c-lcd-driver ```

Build and flash the code to your ESP32:

  ```  idf.py build flash ```

## Usage

Define the GPIO pins used for 4-bit mode operations in the lcd_pins_t structure. Adjust the pin configuration according to your hardware setup.

### Initialize the I2C master:


```
esp_err_t i2c_master_init(void);
```
Use the provided functions to interact with the LCD:

### Initialize the LCD screen:

```
i2c_lcd_init_sequence(int address);
```
### Send a command or data to the LCD:
```
i2c_lcd_send_command(int rs_state, int comm, int address);
```
### Write a message to the LCD:
```
i2c_lcd_write_message(char* msg, int address);
```
### Clear the LCD screen:
```
i2c_lcd_clear_screen(int address);
```
### Define a custom character:
```
i2c_lcd_custom_char(int* pattern[], int location, int address);
```
### Move the cursor to specified coordinates:
```
        i2c_lcd_shift_cursor(int x, int y, int direction, int address);
```
## Contributing

Contributions are welcome! If you find any issues or have improvements to suggest, please open an issue or submit a pull request.
## License
[GPL v2](https://www.gnu.org/licenses/old-licenses/gpl-2.0.txt)
This project is licensed under the MIT License - see the LICENSE.md file for details.
