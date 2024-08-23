#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.
AC_INIT([fbv],[1.1])
AC_CONFIG_SRCDIR([main.c])
AM_INIT_AUTOMAKE([foreign no-dependencies])
AC_CONFIG_HEADERS([config.h])
AC_CANONICAL_HOST

# Checks for programs.
AC_PROG_CC

# Checks for header files.
AC_CHECK_HEADERS([fcntl.h stdlib.h string.h sys/ioctl.h sys/time.h termios.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_INLINE

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_CHECK_FUNCS([munmap select strerror])

# Checks for libraries.
AC_SEARCH_LIBS([png_create_read_struct], [png], [
	LIBS="-lpng"
	CFLAGS="$CFLAGS -DFBV_SUPPORT_PNG"
	], [
	]
)

AC_SEARCH_LIBS([jpeg_start_decompress], [jpeg], [
	LIBS="$LIBS -ljpeg"
	CFLAGS="$CFLAGS -DFBV_SUPPORT_JPEG"
	], [
	]
)

CFLAGS="$CFLAGS -DFBV_SUPPORT_BMP"

AC_CONFIG_FILES([Makefile])
AC_OUTPUT
