FROM fedora

ARG v=11.0.2

# `which` is needed by `make`
# `mesa-libGL` & `libXmu` is needed to compile geant4 application
# `openssl` is needed to download geant4 datasets
RUN  dnf install -y gcc-c++ which mesa-libGL libXmu openssl \
  && dnf clean all && rm -fr /var/cache/*

# get pre-compiled geant4
RUN  curl -LO http://geant4-data.web.cern.ch/releases/lib_$v/Linux-g++8.3.0-CC7.tar.gz \
  && tar xfvz Linux-g++8.3.0-CC7.tar.gz && rm -r Linux-g++8.3.0-CC7.tar.gz \
  && mv Geant4-$v-Linux/bin/* usr/bin && mv Geant4-$v-Linux/lib64/* usr/lib64 \
  && mv Geant4-$v-Linux/include/* usr/include && mv Geant4-$v-Linux/share/* usr/share \
  && sed -i "s|afs/cern.ch/user/g/gunter/l/releases/web/$v/install/Geant4-$v-Linux|usr|g" usr/bin/geant4.sh \
  && sed -i "s|afs/cern.ch/user/g/gunter/l/releases/web/$v/install/Geant4-$v-Linux|usr|g" usr/bin/geant4-config \
  && rm -fr /Geant4-$v-Linux

# download geant4 datasets
RUN geant4-config --install-datasets

# compile GEARS
RUN cd usr/bin \
  && curl -LO https://github.com/jintonic/gears/raw/master/gears.cc \
  && curl -LO https://github.com/jintonic/gears/raw/master/Makefile \
  && make && rm -f gears.cc Makefile /root/*.cfg /root/*.log

WORKDIR root

# avoid using ENV to hard code datasets' locaitons
COPY entrypoint.sh /bin/entrypoint.sh
RUN chmod 755 /bin/entrypoint.sh
ENTRYPOINT ["/bin/entrypoint.sh"]
CMD ["gears"]
