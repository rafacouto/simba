st-link
-------

.. code:: text

   sudo apt install libusb-1.0-0-dev gdb-arm-none-eabi
   git clone https://github.com/eerimoq/stlink
   cd stlink
   ./autogen.sh
   ./configure
   make
   sudo make install
   sudo cp etc/udev/rules.d/49* /etc/udev/rules.d
   sudo udevadm control --reload-rules
   sudo udevadm trigger

   sudo modprobe -r usb-storage && modprobe usb-storage quirks=483:3744:i

   st-util -1
   arm-none-eabi-gdb app.out
   $ target extended-remote localhost:4242

Plug in the board in the PC.

Pin functions
-------------

These are the default pin functions in Simba.

+-------------+--------+
|  Function   |  Pin   |
+=============+========+
|  UART0 TX   |  PA9   |
+-------------+--------+
|  UART0 RX   |  PA10  |
+-------------+--------+
|  UART1 TX   |  PA2   |
+-------------+--------+
|  UART1 RX   |  PA3   |
+-------------+--------+
|  UART2 TX   |  PC10  |
+-------------+--------+
|  UART2 RX   |  PC11  |
+-------------+--------+
|  SPI0 SCK   |  PA5   |
+-------------+--------+
|  SPI0 MISO  |  PA6   |
+-------------+--------+
|  SPI0 MOSI  |  PA7   |
+-------------+--------+
|  I2C0 SCL   |  PB8   |
+-------------+--------+
|  I2C0 SDA   |  PB9   |
+-------------+--------+
