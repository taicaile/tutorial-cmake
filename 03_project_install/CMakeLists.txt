PROJECT(HELLO)
ADD_SUBDIRECTORY(src bin)

# default CMAKE_INSTALL_PREFIX
# /usr/local

# install files
INSTALL(FILES COPYRIGHT README DESTINATION share/doc/cmake)
# install scripts
INSTALL(PROGRAMS runhello.sh DESTINATION bin)
# install directory
INSTALL(DIRECTORY doc/ DESTINATION share/doc/cmake)
