COMMON_REPO := ../../..

#Common Includes
include $(COMMON_REPO)/utility/boards.mk
include $(COMMON_REPO)/libs/xcl/xcl.mk
include $(COMMON_REPO)/libs/opencl/opencl.mk
include $(COMMON_REPO)/libs/oclHelper/oclHelper.mk

# Host Application
concurrent_execution_SRCS=./src/host.cpp $(oclHelper_SRCS) $(xcl_SRCS)
concurrent_execution_HDRS=$(xcl_HDRS)
concurrent_execution_CXXFLAGS=-I./src/ $(opencl_CXXFLAGS) $(xcl_CXXFLAGS) $(oclHelper_CXXFLAGS) -std=c++0x
concurrent_execution_LDFLAGS=$(opencl_LDFLAGS)

EXES=concurrent_execution

# Kernel
matrix_ops_SRCS=./src/matrix_ops.cl

XOS=matrix_ops

# xclbin
matrix_ops_XOS=matrix_ops

XCLBINS=matrix_ops

# check
check_EXE=concurrent_execution
check_XCLBINS=matrix_ops

CHECKS=check

include $(COMMON_REPO)/utility/rules.mk
