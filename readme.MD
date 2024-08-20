# GPIO Interrupt Handler

This project contains kernel modules for handling GPIO interrupts. Below are the details for building, loading, and managing these kernel modules.


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