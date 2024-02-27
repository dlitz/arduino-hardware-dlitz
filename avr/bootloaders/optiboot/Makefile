OPTIBOOT_DIR = ../src/optiboot/optiboot/bootloaders/optiboot
OPTIBOOT_BUILD_OPTS = NODATE=1 LED_START_FLASHES=5

all: optiboot_20MHz

optiboot_20MHz: optiboot_20MHz_atmega328.hex optiboot_20MHz_atmega328.lst

optiboot_20MHz_atmega328.hex optiboot_20MHz_atmega328.lst:
	rm -f \
		$(OPTIBOOT_DIR)/optiboot_atmega328.elf \
		$(OPTIBOOT_DIR)/optiboot_atmega328.lst \
		$(OPTIBOOT_DIR)/optiboot_atmega328.hex
	$(MAKE) -C $(OPTIBOOT_DIR) atmega328 $(OPTIBOOT_BUILD_OPTS) AVR_FREQ=20000000L
	cp -fT $(OPTIBOOT_DIR)/optiboot_atmega328.lst optiboot_20MHz_atmega328.lst
	cp -fT $(OPTIBOOT_DIR)/optiboot_atmega328.hex optiboot_20MHz_atmega328.hex
	$(MAKE) clean_srcdir

clean_srcdir:
	$(MAKE) -C $(OPTIBOOT_DIR) clean
	git -C $(OPTIBOOT_DIR) checkout HEAD -- \*.hex \*.lst

clean: clean_srcdir
	rm -f *.hex *.lst

.PHONY: all clean optiboot_20MHz
.NOTPARALLEL:
