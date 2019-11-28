This document describes the installation of JavaFX on a RaspberryPi

## Update Java to version 1.8.0_201

- Download the package from https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html (here you need "Linux ARM 32 Hard Float ABI")
- Move package to Raspberry to /home/pi (with FileZilla or WinSCP)
- Unpack package
  - ```sudo tar zxvf jdk-8u201-linux-arm32-vfp-hflt.tar.gz -C /opt```
- Enable Java and delete packages
  - ```sudo update-alternatives --install /usr/bin/javac javac /opt/jdk1.8.0_201/bin/javac 1```
  - ```sudo update-alternatives --install /usr/bin/java java /opt/jdk1.8.0_201/bin/java 1```
  - ```rm jdk-8u201-linux-arm32-vfp-hflt.tar.gz```
  - ```sudo update-alternatives --config javac``` **Here with selection 1 Select version 1.8.0_201**
  - ```sudo update-alternatives --config java```  **Here with selection 1 Select version 1.8.0_201**
  - Test if it works with ``` java -version```


## Install JavaFX

- Download the package from https://gluonhq.com/products/mobile/javafxports/get/ (here you need "JavaFX Embedded SDK")
- Move package to Raspberry to /home/pi (with FileZilla or WinSCP)
- Unpack package
  - ```unzip armv6hf-sdk-8.60.9.zip```
- move JavaFX in the java folder
  - ```sudo cp armv6hf-sdk/rt/lib/ext/jfxrt.jar /opt/jdk1.8.0_201/jre/lib/ext/```
  - ```sudo cp armv6hf-sdk/rt/lib/arm/* /opt/jdk1.8.0_201/jre/lib/arm/```
  - ```sudo cp armv6hf-sdk/rt/lib/javafx.platform.properties /opt/jdk1.8.0_201/jre/lib/```
  - ```sudo cp armv6hf-sdk/rt/lib/javafx.properties /opt/jdk1.8.0_201/jre/lib/```
  - ```sudo cp armv6hf-sdk/rt/lib/jfxswt.jar /opt/jdk1.8.0_201/jre/lib/```
- delete the package again
  - ```rm armv6hf-sdk -d -r```