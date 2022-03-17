FROM nps-host:11.2.2.1

RUN yum -y install wget

RUN mkdir /tmp/TSM-Client; \
    wget -q http://9.30.95.172/8.1.10.0-TIV-TSMBAC-LinuxX86.tar -P /tmp/TSM-Client; \
    tar -xvf  /tmp/TSM-Client/8.1.10.0-TIV-TSMBAC-LinuxX86.tar -C /tmp/TSM-Client; \
    rpm -ivh /tmp/TSM-Client/gskcrypt64-8.0.55.14.linux.x86_64.rpm \
    /tmp/TSM-Client/gskssl64-8.0.55.14.linux.x86_64.rpm \
    /tmp/TSM-Client/TIVsm-API64.x86_64.rpm \
    /tmp/TSM-Client/TIVsm-APIcit.x86_64.rpm \
    /tmp/TSM-Client/TIVsm-BA.x86_64.rpm \
    /tmp/TSM-Client/TIVsm-BAcit.x86_64.rpm \
    /tmp/TSM-Client/TIVsm-BAhdw.x86_64.rpm; \
    rm -rf /tmp/TSM-Client  
RUN echo "TSM Client installation is complete"

RUN echo "Link TSM configuration files to persistent storage."
RUN ln -sf /data/opt/tivoli/tsm/client/api/bin64/dsm.sys /opt/tivoli/tsm/client/api/bin64/dsm.sys
RUN ln -sf /data/opt/tivoli/tsm/client/api/bin64/dsm.opt /opt/tivoli/tsm/client/api/bin64/dsm.opt 
