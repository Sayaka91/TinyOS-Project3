COMPONENT=RadioSenseAppC
TOSMAKE_PRE_EXE_DEPS = RadioSenseMsg.py RadioSenseMsg.class
CFLAGS += -DCC2420_NO_ACKNOWLEDGEMENTS
CFLAGS += -DCC2420_NO_ADDRESS_RECOGNITION
CFLAGS += -DTASKLET_IS_TASK


RadioSenseMsg.py: RadioSense.h
	nescc-mig python $(NESC_PFLAGS) $(CFLAGS) -python-classname=RadioSenseMsg RadioSense.h radio_sense_msg -o $@


RadioSenseMsg.class: RadioSenseMsg.java
	javac -cp tinyos.jar RadioSenseMsg.java

RadioSenseMsg.java: RadioSense.h
	nescc-mig java $(NESC_PFLAGS) $(CFLAGS) -java-classname=RadioSenseMsg RadioSense.h radio_sense_msg -o $@


TINYOS_ROOT_DIR?=../../../..
include $(TINYOS_ROOT_DIR)/Makefile.include
