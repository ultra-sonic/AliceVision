# Headers
set(system_files_headers
  cpu.hpp
  gpu.hpp
  MemoryInfo.hpp
  system.hpp
  Timer.hpp
  Logger.hpp
)

# Sources
set(system_files_sources
  cpu.cpp
  MemoryInfo.cpp
  Timer.cpp
  Logger.cpp
)

add_library(aliceVision_system
  ${system_files_headers}
  ${system_files_sources}
)

set_property(TARGET aliceVision_system
  PROPERTY FOLDER AliceVision/AliceVision
)

target_link_libraries(aliceVision_system ${Boost_LIBRARIES})

set_target_properties(aliceVision_system
  PROPERTIES SOVERSION ${ALICEVISION_VERSION_MAJOR}
  VERSION "${ALICEVISION_VERSION_MAJOR}.${ALICEVISION_VERSION_MINOR}"
)

install(TARGETS aliceVision_system
  DESTINATION lib/
  EXPORT aliceVision-targets
)

