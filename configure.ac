AC_INIT(php-fpm, 0.6.0, andrei.nigmatulin@gmail.com)
AM_INIT_AUTOMAKE
AC_CONFIG_SRCDIR([src])
AC_CONFIG_HEADER([src/fpm_autoconfig.h])

AC_SEARCH_LIBS(socket, socket)
AC_SEARCH_LIBS(inet_addr, nsl)

AC_PROG_CC
AC_PROG_CPP
AC_PROG_INSTALL
AC_PROG_LIBTOOL

AC_FPM_CC
AC_FPM_PATHS
AC_FPM_PHP
AC_FPM_LIBXML
AC_FPM_PRCTL
AC_FPM_CLOCK
AC_FPM_TRACE
AC_FPM_LIBEVENT_EMBEDDED

AC_CHECK_FUNCS(setenv clearenv)

AC_CHECK_HEADERS([errno.h fcntl.h stdio.h stdlib.h unistd.h sys/uio.h])
AC_CHECK_HEADERS([sys/select.h sys/socket.h sys/time.h])
AC_CHECK_HEADERS([arpa/inet.h netinet/in.h])

php_fpm_ADD_CFLAGS="$LIBEVENT_CFLAGS $LIBXML_CFLAGS"
php_fpm_ADD_LIBS="$LIBEVENT_LIBS $LIBXML_LIBS $PHP_EXTRA_LIBS"


AC_SUBST(AM_CFLAGS)
AC_SUBST(LIBS)

AC_SUBST(php_fpm_ADD_CFLAGS)
AC_SUBST(php_fpm_ADD_LIBS)

AC_DEFINE_UNQUOTED(PHP_FPM_VERSION, "$PACKAGE_VERSION", [fpm version])

AC_SUBST(php_fpm_conf_path)
AC_DEFINE_UNQUOTED(PHP_FPM_CONF_PATH, "$php_fpm_conf_path", [fpm conf file path])

AC_SUBST(php_fpm_log_path)
AC_DEFINE_UNQUOTED(PHP_FPM_LOG_PATH, "$php_fpm_log_path", [fpm log file path])

AC_SUBST(php_fpm_pid_path)
AC_DEFINE_UNQUOTED(PHP_FPM_PID_PATH, "$php_fpm_pid_path", [fpm pid file path])


AC_CONFIG_FILES([Makefile src/Makefile src/sapi/Makefile src/fpm/Makefile])

AC_OUTPUT(src/php-fpm.conf:conf/php-fpm.conf.in src/init.d.php-fpm:init.d/php-fpm.in)
