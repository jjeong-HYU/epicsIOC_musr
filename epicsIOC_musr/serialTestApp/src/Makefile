TOP=../..

include $(TOP)/configure/CONFIG
#----------------------------------------
#  ADD MACRO DEFINITIONS AFTER THIS LINE
#=============================

#=============================
# Build the IOC application

PROD_IOC = serialTest

serialTest_SNCFLAGS += +r
# serialTest.dbd will be created and installed
DBD += serialTest.dbd

# serialTest.dbd will be made up from these files:
serialTest_DBD += base.dbd
serialTest_DBD += asyn.dbd
serialTest_DBD += calc.dbd
serialTest_DBD += stream.dbd

# Include dbd files from all support applications:
#serialTest_DBD += xxx.dbd
serialTest_DBD +=drvAsynIPPort.dbd
serialTest_DBD +=drvAsynSerialPort.dbd

# Add all the support libraries needed by this IOC
#serialTest_LIBS += xxx
serialTest_LIBS += asyn stream calc

# serialTest_registerRecordDeviceDriver.cpp derives from serialTest.dbd
serialTest_SRCS += serialTest_registerRecordDeviceDriver.cpp

# Build the main IOC entry point on workstation OSs.
serialTest_SRCS_DEFAULT += serialTestMain.cpp
serialTest_SRCS_vxWorks += -nil-

# Add support from base/src/vxWorks if needed
#serialTest_OBJS_vxWorks += $(EPICS_BASE_BIN)/vxComLibrary

# Finally link to the EPICS Base libraries
serialTest_LIBS += $(EPICS_BASE_IOC_LIBS)
#serialTest_LIBS += seq pv
#===========================

include $(TOP)/configure/RULES
#----------------------------------------
#  ADD RULES AFTER THIS LINE

