FROM ubuntu:20.04

# Install docker requirements
RUN apt-get update -qq && apt-get install -qqy \
    apt-transport-https \
    ca-certificates \
    curl \
    lxc \
    iptables \
    apparmor-easyprof \
    apparmor-notify \
    apparmor-utils \
    apparmor-profiles
    
# Install Docker from Docker Inc. repositories.
RUN curl -sSL https://get.docker.com/ | sh

# Install the script.
ADD ./daemonscript /root/daemonscript
RUN chmod +x /root/daemonscript

# Define additional metadata for our image.
VOLUME /var/lib/docker

#Run docker daemon
CMD ["/root/daemonscript"]