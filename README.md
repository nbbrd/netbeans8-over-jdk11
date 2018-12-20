- # netbeans8-over-jdk11

This project purpose is to allow applications based on NetBeans Platform 8 to run on JDK 11.

## Installation

1. Download the [latest release](https://github.com/nbbrd/netbeans8-over-jdk11/releases/latest)
2. Extract it to any folder on your system 
3. Edit the config of the NetBeans Platform Application
  - set the `jdkhome` param to the JDK11 path
  - set the `extra_clusters` param to the extracted folder path

## Current limitations

- Removed class/methods are not emulated and therefore will trigger an exception if used
- The included modules are limited to 
  - `java.xml.bind` (JAXB)
  - `java.activation` (JAF)
  - `java.xml.ws.annotation` (Common Annotations)
  - `java.xml.ws` (JAX-WS)
  - `java.transaction` (JTA)
- NetBeans Platform class loader fails to load `package-info` classes in some cases. One consequence is that JAXB annotations (such as `XMLSchema`) are not parsed and the resulting XML is incomplete.
