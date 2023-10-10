# file(GLOB ALL_C *.c)

add_library(
  fc
  OBJECT
  fc_core.c
	fc_connection.c
	fc_server.c
	fc_client.c
	fc_slab.c
	fc_item.c
	fc_itemx.c
	fc_memcache.c
	fc_message.c
	fc_request.c			
	fc_response.c			
	fc_mbuf.c
	fc_signal.c
	fc_event.c
	fc_time.c
	fc_sha1.c
	fc_log.c
	fc_string.c
	fc_array.c
	fc_util.c
	fc_stats.c
)

# target_link_libraries(storage sqlite3)
# target_link_libraries(storage jsoncpp_lib)

set(ALL_OBJECT_FILES
  ${ALL_OBJECT_FILES} $<TARGET_OBJECTS:fc>
  PARENT_SCOPE)


# add_library(fc_lib STATIC ${ALL_OBJECT_FILES})

add_executable(fatcache fc.cpp)
target_link_libraries(fatcache 
  fc
)

add_compile_definitions(PACKAGE="fatcache")
# add_compile_definitions(PACKAGE_BUGREPORT="manj@twitter.com")
# add_compile_definitions(PACKAGE_NAME="fatcache")
# add_compile_definitions(PACKAGE_STRING="fatcache 0.1.1")
# add_compile_definitions(PACKAGE_TARNAME="fatcache")
# add_compile_definitions(PACKAGE_URL="")
# add_compile_definitions(PACKAGE_VERSION="0.1.1")
# add_compile_definitions(FC_VERSION_STRING="FC_MAJOR.FC_MINOR.FC_PATCH")

add_compile_definitions(FC_MAJOR=0)
add_compile_definitions(FC_MINOR=1)
add_compile_definitions(FC_PATCH=1)
add_compile_definitions(FC_BUGS="manj@twitter.com")
# m4_define([FC_MAJOR], 0)
# m4_define([FC_MINOR], 1)
# m4_define([FC_PATCH], 1)
# m4_define([FC_BUGS], [manj@twitter.com])

add_compile_definitions(FC_VERSION_MAJOR=0)
add_compile_definitions(FC_VERSION_MINOR=1)
add_compile_definitions(FC_VERSION_PATCH=1)
add_compile_definitions(FC_VERSION_STRING="FC_MAJOR.FC_MINOR.FC_PATCH")
# AC_DEFINE(FC_VERSION_MAJOR, FC_MAJOR, [Define the major version number])
# AC_DEFINE(FC_VERSION_MINOR, FC_MINOR, [Define the minor version number])
# AC_DEFINE(FC_VERSION_PATCH, FC_PATCH, [Define the patch version number])
# AC_DEFINE(FC_VERSION_STRING, "FC_MAJOR.FC_MINOR.FC_PATCH", [Define the version string])


add_compile_definitions(HAVE_LITTLE_ENDIAN=1)
# Check if we're a little-endian or a big-endian system
# AC_C_BIGENDIAN(
#   [AC_DEFINE(HAVE_BIG_ENDIAN, 1, [Define to 1 if machine is big endian])],
#   [AC_DEFINE(HAVE_LITTLE_ENDIAN, 1, [Define to 1 if machine is little endian])],
#   [AC_MSG_ERROR([endianess of this machine is unknown])],
#   [AC_MSG_ERROR([universial endianess not supported])]
# )

# Check whether to enable debug logs and asserts
# AC_MSG_CHECKING([whether to enable debug logs and asserts])
# AC_ARG_ENABLE([debug],
#   [AS_HELP_STRING(
#     [--enable-debug=@<:@full|yes|log|no@:>@],
#     [enable debug logs and asserts @<:@default=no@:>@])
#   ],
#   [],
#   [enable_debug=no])
# AS_CASE([x$enable_debug],
#   [xfull], [AC_DEFINE([HAVE_ASSERT_PANIC], [1],
#                       [Define to 1 if panic on an assert is enabled])
#             AC_DEFINE([HAVE_DEBUG_LOG], [1], [Define to 1 if debug log is enabled])
#            ],
#   [xyes], [AC_DEFINE([HAVE_ASSERT_LOG], [1],
#                      [Define to 1 if log on an assert is enabled])
#            AC_DEFINE([HAVE_DEBUG_LOG], [1], [Define to 1 if debug log is enabled])
#           ],
#   [xlog], [AC_DEFINE([HAVE_DEBUG_LOG], [1], [Define to 1 if debug log is enabled])],
#   [xno], [],
#   [AC_MSG_FAILURE([invalid value ${enable_debug} for --enable-debug])])
# AC_MSG_RESULT([$enable_debug])

# Define Makefiles
# AC_CONFIG_FILES([Makefile
#                  src/Makefile
#                  src_test/Makefile])

# PACKAGE = fatcache
# PACKAGE_BUGREPORT = manj@twitter.com
# PACKAGE_NAME = fatcache
# PACKAGE_STRING = fatcache 0.1.1
# PACKAGE_TARNAME = fatcache
# PACKAGE_URL = 
# PACKAGE_VERSION = 0.1.1


# add_executable(test_scenario_2_side0 ${ROOT_DIR}/test/test_scenario_2/test_scenario_2_side0/test_scenario_2_side0.cpp)
add_compile_definitions(_GNU_SOURCE)