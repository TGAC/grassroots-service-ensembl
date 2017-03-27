# Ensembl service

The Ensembl service allows the Grassroots Server to use the functionality provided by the [Ensembl REST API](http://rest.ensemblgenomes.org/). Currently only the ability to search for sequences by identifier is implemented. 

## Installation

To build this service, you need the [grassroots core](https://github.com/TGAC/grassroots-core) and [grassroots build config](https://github.com/TGAC/grassroots-build-config) installed and configured. 

The files to build the Ensembl service are in the ```build/<platform>``` directory. 

### Linux

If you enter this directory 

```cd build/linux```

you can then build the service by typing

```make all```

and then 

```make install```

to install the service into the Grassroots system where it will be available for use immediately.
