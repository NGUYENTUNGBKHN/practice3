PROJ_DIR=./..
OUT_DIR=bin
OUT_OBJ_FILE=bin/obj

TARGET=main

.PHONY: all clean

#toolchain
CXX=g++

# include
INC_DIR=

# source
SRC_FILES= main.cpp

INC_FOLDERS =

OBJSCPP = $(patsubst %.cpp, $(OUT_OBJ_FILE)/%.opp,$(SRC_FILES))

CPP_FLAG += -D_UNICODE

all: $(START) $(TARGET)

$(START):
	echo "COMPILE START"

$(TARGET): $(OBJSCPP)
	@echo "LINK $@"
	@mkdir -p $(shell dirname $@)
	@$(CXX) -o $(OUT_DIR)/$@ $^ $(CPP_FLAG)

$(OUT_OBJ_FILE)/%.opp: %.cpp
	@echo "CXX $@"
	@mkdir -p $(shell dirname $@)
	@$(CXX) $(CPP_FLAG) $(INC_FOLDERS) -c $< -o $@
