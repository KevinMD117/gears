FROM physino/root

# jupyter notebook to run ROOT and python scripts
RUN  dnf install -y root-notebook \
  && dnf clean all && rm -fr /var/cache/* \
  && pip install uproot awkward
