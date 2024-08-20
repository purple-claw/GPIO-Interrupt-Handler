# Makefile for bottom.c

# Compiler
CC = gcc

# Module name
MODULE_NAME = bottom

# Kernel source directory
KERNEL_SRC = /lib/modules/$(shell uname -r)/build

# Source files
SRC = bottom.c

# Object files
OBJ = $(SRC:.c=.o)

# Default target
all: $(MODULE_NAME).ko

# Compile the kernel module
$(MODULE_NAME).ko: $(OBJ)
    $(MAKE) -C $(KERNEL_SRC) M=$(PWD) modules

# Compile the object file
%.o: %.c
    $(CC) -c -o $@ $<

# Clean up
clean:
    $(MAKE) -C $(KERNEL_SRC) M=$(PWD) clean
    rm -f $(OBJ) $(MODULE_NAME).ko

.PHONY: all clean