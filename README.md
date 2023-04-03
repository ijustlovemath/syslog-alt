The goal of this project is to create the backend library and corresponding daemon for a simple syslog-like interface.

## Requirements

0. There should be a shared library for implementing the interface, and a daemon which handles the logging.

1. The C API of this library should exactly match the normal syslog found on Linux systems.

2. The syslog should support multiple simultaneous writers without interleaving.

3. The daemon that handles syslog requests should default to logging to "/tmp/alt-syslog.log", which can be overridden with a `-f /path/to/log` location. Insufficient access to create this log should be detected, and the daemon should fail to start if this isn't available.
