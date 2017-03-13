NAME 		:= ensembl_rest_service
DIR_SRC := $(realpath ../../src)
DIR_INCLUDE :=$(realpath ../../include)
DIR_BUILD :=  $(realpath .)
CC		:= gcc
CXX		:= g++
MAKEDEPEND 	:= gcc -MM -MF


BUILD		:= debug

ifeq ($(DIR_BUILD_UTILS),)
export DIR_BUILD_UTILS = $(abspath $(realpath ../../../../build_utils/linux))
endif

include $(DIR_BUILD_UTILS)/project.properties

export DIR_INSTALL=$(DIR_GRASSROOTS_INSTALL)/services

VPATH	= \
	$(DIR_SRC) 
	

INCLUDES = \
	-I$(DIR_INCLUDE) \
	-I$(DIR_GRASSROOTS_UTIL_INC) \
	-I$(DIR_GRASSROOTS_UTIL_INC)/containers \
	-I$(DIR_GRASSROOTS_UTIL_INC)/io \
	-I$(DIR_GRASSROOTS_NETWORK_INC) \
	-I$(DIR_GRASSROOTS_SERVICES_INC) \
	-I$(DIR_GRASSROOTS_PARAMS_INC) \
	-I$(DIR_GRASSROOTS_HANDLER_INC) \
	-I$(DIR_JANSSON_INC) \
	-I$(DIR_UUID_INC)
	
	
SRCS 	= \
	ensembl_rest_service.c \
	sequence.c 	
	 
CPPFLAGS += -DENSEMBL_REST_LIBRARY_EXPORTS 

LDFLAGS += -L$(DIR_JANSSON_LIB) -ljansson -L$(DIR_GRASSROOTS_UTIL_LIB) -l$(GRASSROOTS_UTIL_LIB_NAME) \
	-L$(DIR_GRASSROOTS_SERVICES_LIB) -l$(GRASSROOTS_SERVICES_LIB_NAME) \
	-L$(DIR_GRASSROOTS_HANDLER_LIB) -l$(GRASSROOTS_HANDLER_LIB_NAME) \
	-L$(DIR_GRASSROOTS_NETWORK_LIB) -l$(GRASSROOTS_NETWORK_LIB_NAME) \
	-L$(DIR_GRASSROOTS_PARAMS_LIB) -l$(GRASSROOTS_PARAMS_LIB_NAME) \
	-lcurl


include $(DIR_BUILD_UTILS)/generic_makefiles/shared_library.makefile


