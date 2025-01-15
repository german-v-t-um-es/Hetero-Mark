# Source files
CPPSRC = main.cc fir_hip_benchmark.cu

# Executable name
EXECUTABLE = fir.gem5

# Optimization level
OPTS = -O1

# HIP paths and compiler
HIP_PATH ?= /opt/rocm/hip
HIPCC = $(HIP_PATH)/bin/hipcc

# GEM5 paths
GEM5_PATH ?= $(shell pwd)/../.gem5

# Compiler and linker flags
CFLAGS += -I$(GEM5_PATH)/include -lz -lm -lc -lpthread -O1
LDFLAGS += -L$(GEM5_PATH)/util/m5/build/x86/out -lm5 \
           -lfir -ltime_measurement -lcommand_line_option -lbenchmark

# GPU targets
TARGET = gfx801,gfx803,gfx902

# Output directory
BIN_DIR ?= ./bin

# Build rules
all: $(BIN_DIR)/$(EXECUTABLE)

$(BIN_DIR)/$(EXECUTABLE): $(CPPSRC) $(BIN_DIR)
	$(HIPCC) $(OPTS) --amdgpu-target=$(TARGET) $(CXXFLAGS) $(CPPSRC) -o $(BIN_DIR)/$(EXECUTABLE) $(CFLAGS) $(LDFLAGS)

$(BIN_DIR):
	mkdir -p $(BIN_DIR)

# Clean rule
clean:
	rm -rf $(BIN_DIR)

.PHONY: all clean
