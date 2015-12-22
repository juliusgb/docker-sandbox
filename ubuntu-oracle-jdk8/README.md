# Ubuntu Oracle JDK 8 Container

Uses [frolvlad's approach](https://hub.docker.com/r/frolvlad/alpine-oraclejdk8/) but modified to work with Ubuntu 14.04.

I found other approaches for creating Oracle JDK containers online, but they didn't provide options to select a particular version of the JDK to install. Nevertheless, I found them useful to create ubuntu-specific commands. E.g., 
* For ubuntu's `apt-sources`, [David Caste's dockerfile](https://hub.docker.com/r/davidcaste/docker-jdk8/~/dockerfile/);
* For removing temporary installer files, [sonodar's dockerfile](https://github.com/sonodar/docker-jdk8/blob/master/Dockerfile).
