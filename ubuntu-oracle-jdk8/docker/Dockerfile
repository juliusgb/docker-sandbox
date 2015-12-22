FROM ubuntu:14.04

ENV JAVA_VERSION=8 \
    JAVA_UPDATE=66 \
    JAVA_BUILD=17 \
    JAVA_HOME="/usr/lib/jvm/default-jvm"
	
RUN apt-get -y install wget ca-certificates \
	&& cd "/tmp" \
	&& wget --header "Cookie: oraclelicense=accept-securebackup-cookie;" \
        "http://download.oracle.com/otn-pub/java/jdk/${JAVA_VERSION}u${JAVA_UPDATE}-b${JAVA_BUILD}/jdk-${JAVA_VERSION}u${JAVA_UPDATE}-linux-x64.tar.gz" \
	&& tar -xzf "jdk-${JAVA_VERSION}u${JAVA_UPDATE}-linux-x64.tar.gz" \
	&& mkdir -p "/usr/lib/jvm" \
	&& mv "/tmp/jdk1.${JAVA_VERSION}.0_${JAVA_UPDATE}" "/usr/lib/jvm/java-${JAVA_VERSION}-oracle"\
	&& ln -s "java-${JAVA_VERSION}-oracle" "$JAVA_HOME" \
	&& ln -s "$JAVA_HOME/bin/"* "/usr/bin/" \
	&& rm -rf "$JAVA_HOME/"*src.zip \
	&& apt-get autoremove -y \
	&& apt-get clean \
	&& rm -rf /tmp/* 
	

# test jdk
RUN mkdir /u01 \
	&&  chmod a+xr /u01 \
	&& mkdir /u01/services \
	&& chmod a+xr /u01/services 

COPY /files/readme.txt /u01/
COPY /files/services/HelloWorld.java /u01/services/ 
RUN javac /u01/services/HelloWorld.java
RUN java -cp /u01 services.HelloWorld

# Define default command.
CMD ["bash"]