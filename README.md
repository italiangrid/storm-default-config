The StoRM Default YAIM Configuration
===============================

StoRM Default YAIM Configuration component contains all the files required to configure a Standalone StoRM
deployment. By providing a coupple of parameters the installation is fully configured to be tested
with StoRM T-StoRM Testsuite

Supported platforms
Scientific Linux 5 on x86_64 architecture
Scientific Linux 6 on x86_64 architecture

### Building
Required packages:

* epel
* git
* automake
* autoconf
* libtool
* rpm-build

Build command:
```bash
./bootstrap
./configure --prefix=/usr --sbindir=/usr/sbin --sysconfdir=/etc --datadir=/usr/share
make rpm
```

# Contact info

If you have problems, questions, ideas or suggestions, please contact us at
the following URLs

* GGUS (official support channel): http://www.ggus.eu
