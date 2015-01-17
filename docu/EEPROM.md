# How to flash/update the ID EEPROM?

The EEPROM on the HAT for Raspberry Pi Model B+ can be updated as follows.
Before the update the **WP** jumper next to the EEPROM has to be closed.

* Install [EEPROM utils](https://github.com/raspberrypi/hats/tree/master/eepromutils):
    ```
    $ git clone https://github.com/raspberrypi/hats
    $ cd hats/eepromutils
    $ make
    $ chmod +x eepflash.sh
    ```

* Generate EEPROM data:
    ```
    $ wget https://github.com/joabakk/RPi-Proto-HAT/raw/master/docu/rpi-proto-hat.txt
    $ ./eepmake rpi-proto-hat.txt rpi-proto-hat.eep
    ```

* Update EEPROM:
    ```
    $ sudo ./eepflash.sh -w -t=24c32 -f=rpi-proto-hat.eep
    ```
