cmake_minimum_required(VERSION 3.8)
project(syslog_alt)

include_directories(include)

# SLA short for "syslog_alt"
add_library(sla SHARED lib/libsyslog_alt.c)


# daemon for logging
add_executable(syslogaltd bin/daemon.c)
target_link_libraries(syslogaltd sla)

# binary for testing
add_executable(tester bin/test_syslog.c)
target_link_libraries(tester sla)
