# GPIO Interrupt Handler

This project contains kernel modules for handling GPIO interrupts. Below are the details for building, loading, and managing these kernel modules.
It demonstrates the use of GPIO pins on a Raspberry Pi (or any other single-board computer like Beagleboards) to handle button presses using interrupts. Instead of continuously polling for input, which can be inefficient and drain battery life, this project leverages interrupts to trigger specific actions when a button is pressed. This is a common technique in embedded systems for improving performance and efficiency, two buttons are connected to GPIO pins 17 and 18, and an LED is connected to GPIO pin 4. When a button is pressed, the corresponding interrupt triggers a function that controls the LED, either turning it on, off, or toggling its state. The GPIO pin numbers can be easily modified to suit different hardware configurations.


## Building the Kernel Modules

### GPIO Module

1. Navigate to the [`GPIO`](command:_github.copilot.openRelativePath?%5B%7B%22scheme%22%3A%22file%22%2C%22authority%22%3A%22%22%2C%22path%22%3A%22%2Fc%3A%2FUsers%2Fhawkr%2FOneDrive%2FDesktop%2FGPIO-Interrupt-Handler%2FGPIO%22%2C%22query%22%3A%22%22%2C%22fragment%22%3A%22%22%7D%5D "c:\Users\hawkr\OneDrive\Desktop\GPIO-Interrupt-Handler\GPIO") directory:
   ```sh
   cd GPIO-Interrupt-Handler/GPIO

2. Build the Kernel module:
    ```sh
    make

### Bottom Half Module
1. Navigate to the bottom_half directory:
    ```sh
    cd GPIO-Interrupt-Handler/bottom_half

2. Build the kernel module:
    ```sh
    make

## Loading the Kernel Module:
### GPIO Module

1. Navigate to GPIO directory:
    ```sh
    cd GPIO-Interrupt-Handler/GPIO

2. Load the kernel module:
    ```sh
    sudo insmod gpio.ko

3. Verify that the module is loaded:
    ```sh
    lsmod | grep gpio

4. Check the Kernel Log for messages:
    ```sh
    dmesg | tail

### Bottom half Module

1. Navigate to bottom_half directory:
    ```sh
    cd GPIO-Interrupt-Handler/bottom_half

2. Load the kernel module:
    ```sh
    sudo insmod bottom.ko

3. Verify that the module is loaded:
    ```sh
    lsmod | grep bottom

4. Check the Kernel Log for messages:
    ```sh
    dmesg | tail

## Unloading the Kernel Modules
### GPIO Module
1.  Unload the Kernel Module:
    ```sh
    sudo rmmod gpio

## Bottom Half Module
1. Unload the Kernel Module:
    ```sh
    sudo rmmod bottom
