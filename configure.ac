AC_PREREQ([2.69])
AC_INIT([autoconf-skel], [0.1.0], [bugs@kara-online.net], [autoconf-skel], [https://github.com/kro-cat/autoconf-skel])

m4_include([m4/ax_valgrind_check.m4])

AC_ARG_ENABLE(debug,
  [AS_HELP_STRING([--enable-debug], [Enable debug messages (default is no)])],
  [enable_debug=$enableval],
  [enable_debug=no]
)

if test "x$enable_debug" = "xyes"; then
	AC_DEFINE([DEBUG], [], [enable debug messages])
	AC_MSG_NOTICE([debug messages will be enabled])
fi

#host switch
AC_CANONICAL_HOST

AS_CASE(["$host_os"],
  [*linux*], [
   # OS specific stuff here
  ],
#  [*mingw*|*cygwin*], [
#   # OS specific stuff here
#    AC_DEFINE([WINVER], [_WIN32_WINNT_WIN10],
#      [Define windows version as WIN10])
#    AC_DEFINE([_WIN32_WINNT], [_WIN32_WINNT_WIN10],
#      [Define windows version as WIN10])
#  ],
  [AC_MSG_WARN([unsupported system: $host_os])]
)

#autoconf stuff
AM_INIT_AUTOMAKE([subdir-objects])
WARN_CFLAGS="-W -Wall -Wunused -Werror"
AC_SUBST(WARN_CFLAGS)
AC_CONFIG_MACRO_DIRS([m4])
#AC_CONFIG_SUBDIRS([include/krossock])
AC_CONFIG_SRCDIR([src/])
AC_CONFIG_HEADERS([config.h])
AX_VALGRIND_DFLT([memcheck], [on])
AX_VALGRIND_CHECK

#program config

#headers

#types

#functions

#makefiles
AC_CONFIG_FILES([
  Makefile
  src/Makefile
  tests/Makefile
  include/Makefile
])
AC_OUTPUT
