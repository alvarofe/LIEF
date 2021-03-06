file(READ "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/enums.inc"      LIEF_MACHO_ENUMS)
file(READ "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/structures.inc" LIEF_MACHO_STRUCTURES)

configure_file(
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/enums.hpp.in"
  "${CMAKE_CURRENT_BINARY_DIR}/include/LIEF/MachO/enums.hpp"
  @ONLY
)

configure_file(
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/Structures.hpp.in"
  "${CMAKE_CURRENT_BINARY_DIR}/include/LIEF/MachO/Structures.hpp"
  @ONLY
)

set(LIEF_MACHO_SRC
  "${CMAKE_CURRENT_LIST_DIR}/utils.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Binary.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/UUIDCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Symbol.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/EnumToString.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Header.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/DynamicSymbolCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Section.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/LoadCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/BinaryParser.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Builder.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/SegmentCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Parser.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/SymbolCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/MainCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/DylibCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/DylinkerCommand.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/DyldInfo.cpp"
  "${CMAKE_CURRENT_LIST_DIR}/Builder.tcc"
  "${CMAKE_CURRENT_LIST_DIR}/Binary.tcc"
  "${CMAKE_CURRENT_LIST_DIR}/BinaryParser.tcc"
  "${CMAKE_CURRENT_LIST_DIR}/FunctionStarts.cpp"
)

set(LIEF_MACHO_INCLUDE_FILES
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/Binary.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/BinaryParser.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/Builder.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/DylibCommand.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/DylinkerCommand.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/EnumToString.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/Header.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/LoadCommand.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/MainCommand.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/Parser.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/Section.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/SegmentCommand.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/Symbol.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/SymbolCommand.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/type_traits.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/utils.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/DyldInfo.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/UUIDCommand.hpp"
  "${CMAKE_CURRENT_SOURCE_DIR}/include/LIEF/MachO/FunctionStarts.hpp"
  "${CMAKE_CURRENT_BINARY_DIR}/include/LIEF/MachO/Structures.hpp"
  "${CMAKE_CURRENT_BINARY_DIR}/include/LIEF/MachO/enums.hpp"
  )

source_group("Header Files\\MachO" FILES ${LIEF_MACHO_INCLUDE_FILES})
source_group("Source Files\\MachO" FILES ${LIEF_MACHO_SRC})

target_sources(LIB_LIEF_STATIC PRIVATE ${LIEF_MACHO_SRC} ${LIEF_MACHO_INCLUDE_FILES})
target_sources(LIB_LIEF_SHARED PRIVATE ${LIEF_MACHO_SRC} ${LIEF_MACHO_INCLUDE_FILES})
