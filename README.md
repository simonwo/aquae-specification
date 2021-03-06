
  Aquae - gov.uk Personal Data Exchange Specification
  ===================================================

  Copyright (C) 2017, The Personal Data Exchange Team, Crown Copyright (Government Digital Service).

## 1. Introduction

gov.uk Personal Data Exchange is a way to query existing personal data
held by government. This distribution is the technical specification
for how the system operates and a set of tools for working with the
messages and protocols defined.

The whole package is distributed under an MIT license and as such is
free to use and modify as long as you agree to its terms.

_Note: Should you have any trouble in setting up and using these tools,
please feel free to contact:_

+ _Andy Bennett <andyjpb@digital.cabinet-office.gov.uk>_
+ _Simon Worthington <simon.worthington@digital.cabinet-office.gov.uk>_

## 2. Specification

The specification is described in the following files:

+ **transport.md**

    This file documents the low-level transport protocols used
    by participants in the system.

+ **metadata.md**

    This file documents the format and structure of the configuration
    file produced.

+ **messaging.md**

    This file documents the format and sequences of messages sent
    by participants in the system.


## 3. Installation

The tools in this package can be run straight away; they do not need to
be built or installed. However, they do have a number of dependencies
which need to be satisfied.

For UNIX systems, the tools require GNU Make and Perl. These tools are
usually available by default or from system packages.

For Windows systems, the tools require PowerShell, which is availble by
default in Windows 10 or from http://msdn.microsoft.com/en-us/powershell.


## 4. Usage

In order to render the specification and build the protocol and
message definition, invoke `make` thus:

    make all

Windows users can install builds of GNU Make, `sh` and `perl`,
and will also need a tool capable of writing `.tar.gz` files, such as 7-Zip.
Then set the following environment varialbles to get full functionality:

    $Env:RM='powershell ''function rm_all { rm -ErrorAction:SilentlyContinue -force $$args }; rm_all'''
    $Env:TAR='"C:/Program Files/7-Zip/7z.exe" a -ttar'
    $Env:GZ='"C:/Program Files/7-Zip/7z.exe" a'

This will produce three files:

+ **transport.proto**

    This contains the Protocol Buffer definitions for the low-level
    transport protocols.

+ **metadata.proto**

    This contains the Protocol Buffer definitions for the metadata
    file that is used to set policy in a federation of Aquae nodes.

+ **messaging.proto**

    This contains the Protocol Buffer definitions for the inter-node
    messaging protocol.


## 5. Examples

The scripts in the `examples/` directory create Aquae Metadata files in
Protobuf Text Format that describes an example Aquae Federation.

These are synthetic examples for testing and may not represent real world entities or usage.

Please consult `examples/README.md` for more information.

## 6. Compatibility notes

This specification is not yet stable and, as such, we make no
guarantees of backwards or forwards compatibility. We do not recommend
that this system is deployed in anger.


## 7. What's next?

First and foremost, enjoy the tools and use and extend them to build
your own Personal Data Exchange Federations.

Please feel free to send tools that you build with this so that they
can be integrated and distributed with this package.

Suggestions, extensions and patches are welcome.

If you have any questions or problems (even the slightest problem, or
the stupidest of questions), then please feel free to get in touch with
us directly using the addresses above. We will try to help you, get you
going or point you in the right direction.
