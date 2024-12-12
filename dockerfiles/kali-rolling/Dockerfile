# DESCRIPTION:
#   This Dockerfile build a docker image based on kalilinux/kali-rolling with
#   additional tools of choice.
#
# BUILD:
#   $ docker build host -f Dockerfile -t local/kali-rolling:latest --build-arg USER=$USER .
#
FROM kalilinux/kali-rolling:latest

ARG USER

ENV KALI_USER=${USER}

RUN apt update && apt dist-upgrade -y  && DEBIAN_FRONTEND=noninteractive apt install -y \
    curl \
    dnsutils \
    git \
    inetutils-ftp \
    inetutils-ping \
    inetutils-telnet \
    fuse \
    libfuse2 \
    libglib2.0-0 \
    libopengl0 \
    libnss3 \
    libatk1.0-0 \
    libatk-bridge2.0-0 \
    libcups2 \
    libdrm2 \
    libgtk-3-0 \
    libgbm1 \
    libasound2 \
    xdg-utils \
    iproute2 \
    net-tools \
    openssh-client \
    sudo \
    tmux \
    vim \
    wget \
    zsh \
    awscli \
    default-mysql-client \
    jq \
    ldapscripts \
    man-db \
    masscan \
    massdns \
    netcat-traditional \
    nfs-common \
    nmap \
    openjdk-17-jdk \
    python3-pip \
    smbclient \
    smbmap \
    sqlmap \
    swaks \
    tcpdump \
    theharvester \
    tree \
    tshark \
    tmux \
    wfuzz \
    whatweb \
    whois \
    wpscan \
    node-ws \
    python3.11-venv \
    onesixtyone \
    snmp \
    xclip \
    zsh-autosuggestions \
    zsh-syntax-highlighting \
    && apt autoremove -y --purge \
    && apt clean -y \
    && rm -rf /var/lib/apt/lists/*

RUN useradd -m -s /bin/zsh -G sudo,video ${KALI_USER} \
    && sed -i 's/^%sudo[[:space:]]ALL=(ALL:ALL)[[:space:]]ALL$/%sudo ALL=(ALL:ALL) NOPASSWD:ALL/' /etc/sudoers
#    && localedef -i en_US -c -f UTF-8 -A /usr/share/locale/locale.alias en_US.UTF-8 

WORKDIR /home/${USER}