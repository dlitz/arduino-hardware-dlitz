To burn the bootloader, connect an FT232R to the ICSP port, then run:

    arduino-cli burn-bootloader -b dlitz:avr:pwmfanctl -P arduino_ft232r -v
