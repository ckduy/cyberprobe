
bin_PROGRAMS = cyberprobe cybermon nhis11-rcvr etsi-rcvr cyberprobe-cli

cyberprobe_SOURCES = cyberprobe.C nhis11.C sender.C \
	delivery.C xml.C capture.C configuration.C control.C snort_alert.C \
	sender.h delivery.h capture.h \
	configuration.h control.h snort_alert.h target.h \
	parameters.h packet_consumer.h interface.h \
	endpoint.h parameter.h
cyberprobe_LDADD = libcybermon.la -lssl

cybermon_SOURCES = cybermon.C management.h 
cybermon_LDADD = libcybermon.la -lssl

cyberprobe_cli_SOURCES = cyberprobe-cli.C readline.C readline.h
cyberprobe_cli_LDADD = libcybermon.la -lssl

nhis11_rcvr_SOURCES = nhis11_rcvr.C nhis11.C
nhis11_rcvr_LDADD = libcybermon.la -lssl

etsi_rcvr_SOURCES = etsi_rcvr.C
etsi_rcvr_LDADD = libcybermon.la -lssl

lib_LTLIBRARIES = libcybermon.la

libcybermon_la_SOURCES = engine.C etsi_li.C socket.C ber.C base_context.C \
	ip.C tcp.C udp.C http.C address.C icmp.C cybermon-lua.C reaper.C \
	unrecognised.C dns.C dns_protocol.C forgery.C smtp.C ftp.C \
	resource_manager.C \
	../include/cybermon/engine.h ../include/cybermon/etsi_li.h \
	../include/cybermon/socket.h ../include/cybermon/ber.h \
	../include/cybermon/base_context.h ../include/cybermon/ip.h \
	../include/cybermon/tcp.h ../include/cybermon/udp.h \
	../include/cybermon/http.h ../include/cybermon/address.h \
	../include/cybermon/icmp.h ../include/cybermon/nhis11.h \
	../include/cybermon/resource.h \
	../include/cybermon/cybermon-lua.h ../include/cybermon/reaper.h \
	../include/cybermon/unrecognised.h ../include/cybermon/dns.h \
	../include/cybermon/dns_protocol.h ../include/cybermon/forgery.h \
	../include/cybermon/smtp.h ../include/cybermon/ftp.h \
	../include/cybermon/thread.h ../include/cybermon/context.h \
	../include/cybermon/pdu.h ../include/cybermon/exception.h \
	../include/cybermon/flow.h ../include/cybermon/manager.h \
	../include/cybermon/observer.h ../include/cybermon/monitor.h \
	../include/cybermon/transport.h \
	../include/cybermon/serial.h ../include/cybermon/protocol.h \
	../include/cybermon/xml.h \
	../include/cybermon/specification.h ../include/cybermon/packet_capture.h

ACLOCAL_AMFLAGS = -I m4

AM_CPPFLAGS = -I$(top_srcdir)/include
AM_LDFLAGS = 

LDFLAGS_BOOST = \
    $(BOOST_REGEX_LDFLAGS) $(BOOST_PROGRAM_OPTIONS_LDFLAGS)

LIBS_BOOST = \
    $(BOOST_REGEX_LIBS) $(BOOST_PROGRAM_OPTIONS_LIBS)

AM_CPPFLAGS += $(BOOST_CPPFLAGS) $(LUA_INCLUDE)
AM_LDFLAGS += $(LDFLAGS_BOOST) $(LUA_LDADD)
LIBS += $(LIBS_BOOST) $(LUA_LIB)

