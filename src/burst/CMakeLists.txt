set(BURST_INCLUDE_DIRS
  ${FB_INCLUDE_DIRS}
  ${RT_INCLUDE_DIRS}
  ${CMAKE_CURRENT_SOURCE_DIR}
  )
list(REMOVE_DUPLICATES BURST_INCLUDE_DIRS)
include_directories(${BURST_INCLUDE_DIRS})

set(burst_old_SOURCES
  Hm.c
  HmGetc.c
  HmGlob.c
  Sc.c
  burst.c
  error.c
  fb.c
  glob.c
  grid.c
  gridrotate.c
  idents.c
  paint.c
  plot.c
  prnt.c
  trie.c
  ui.c
  )


BRLCAD_ADDEXEC(burst "${burst_old_SOURCES}" "librt;libdm;${M_LIBRARY}")
ADD_TARGET_DEPS(burst dm_plugins)

# Burst coding style is very old, and tool is deprecated.  Not worth
# updating it to satisfy the strict-prototypes flag
include(CheckCXXCompilerFlag)
check_cxx_compiler_flag(-Wno-strict-prototypes NO_STRICT_PROTO_COMPILER_FLAG)
if (NO_STRICT_PROTO_COMPILER_FLAG)
  # If we have the Wno-strict-prototypes flag, use it
  target_compile_options(burst PRIVATE "-Wno-strict-prototypes")
endif (NO_STRICT_PROTO_COMPILER_FLAG)

set(burst_old_noinst_HEADERS
  CMakeLists.txt
  ascii.h
  burst.h
  extern.h
  Mm.h
  Sc.h
  )
CMAKEFILES(${burst_old_noinst_HEADERS})

# Local Variables:
# tab-width: 8
# mode: cmake
# indent-tabs-mode: t
# End:
# ex: shiftwidth=2 tabstop=8
