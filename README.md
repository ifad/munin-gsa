Munin-GSA
=========

Google Search Appliance SNMP plugin for Munin. SNMP autoconf is
supported, and munin-node-configure works as expected.

APPLICABLE SYSTEMS
------------------

A GSA running software version 5.0 or above. See [1] for counters
exported via SNMP. Usage of SNMPv3 is recommended, with AuthPriv,
and the SHA authentication scheme.

CONFIGURATION
-------------

Create a "Munin" user on the GSA SNMP configuration, and then use
something similar to the following:

    [snmpv3_gsa.host.name_*]
      env.v3username munin
      env.v3authprotocol sha
      env.v3authpassword your-auth-passwd
      env.v3privprotocol des
      env.v3privpassword your-priv-passwd

Please see 'perldoc Munin::Plugin::SNMP' for further configuration
information.

INTERPRETATION
--------------

The graph shows statistics about the documents index and queries per minute.

MIB INFORMATION
---------------

This plugin requires the GOOGLE-MIB and GSA-MIB and will report

GSA-MIB::docsServed.0 = INTEGER: ..
GSA-MIB::docErrors.0 = INTEGER: ...
GSA-MIB::docsFound.0 = INTEGER: ...
GSA-MIB::docBytes.0 = INTEGER: ....
GSA-MIB::qpm.0 = INTEGER: .........

AUTHOR
------

Marcello Barnaba <vjt@openssl.it>
