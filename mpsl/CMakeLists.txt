#
# Copyright (c) 2018 Nordic Semiconductor
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#

nrfxlib_calculate_lib_path(MPSL_LIB_PATH
  BASE_DIR ${CMAKE_CURRENT_SOURCE_DIR}
  SOFT_FLOAT_FALLBACK
)

if(NOT MPSL_LIB_PATH)
  message(WARNING "This combination of SoC and floating point ABI is not supported by the MPSL lib.")
endif()

zephyr_include_directories(include)
zephyr_include_directories(include/protocol)
zephyr_link_libraries(${MPSL_LIB_PATH}/libmpsl.a)
