include(GSSBuild NO_POLICY_SCOPE)

project(ssdp-responder 
    VERSION 1.0.0 
    DESCRIPTION "This is the cross platform project for ssdp-responder"
    HOMEPAGE_URL  https://github.com/troglobit/ssdp-responder
    LANGUAGES C)

cmake_minimum_required(VERSION 3.22)

GSS_ADD_EXECUTABLE(ssdpd  SOURCES src/ssdpd.c src/netlink.c src/ssdp.c src/web.c lib/strlcpy.c lib/pidfile.c)

set_property(TARGET ssdpd PROPERTY C_STANDARD 11)

target_include_directories(ssdpd PRIVATE src)

GSS_PACK()