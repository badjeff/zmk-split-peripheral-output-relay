zephyr_library()

if (CONFIG_ZMK_SPLT_PERIPHERAL_OUTPUT_RELAY)

  if (CONFIG_ZMK_SPLIT_ROLE_CENTRAL)
    zephyr_library_sources(src/output_relay_central.c)
  endif()

  if (CONFIG_ZMK_SPLIT AND (NOT CONFIG_ZMK_SPLIT_ROLE_CENTRAL))
    zephyr_library_sources(src/output_relay_peripheral.c)
  endif()

  zephyr_include_directories(include)

  zephyr_include_directories(${APPLICATION_SOURCE_DIR}/include)

endif()
