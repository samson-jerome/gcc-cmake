FROM gcc:8

RUN wget https://github.com/Kitware/CMake/releases/download/v3.15.5/cmake-3.15.5-Linux-x86_64.sh \
      -q -O /tmp/cmake-install.sh \
      && chmod u+x /tmp/cmake-install.sh \
      && mkdir /usr/bin/cmake \
      && /tmp/cmake-install.sh --skip-license --prefix=/usr/bin/cmake \
      && rm /tmp/cmake-install.sh

RUN apt-get update && apt-get install -y --no-install-recommends \
      zlib1g-dev libbz2-dev libsnappy-dev \
      && apt-get clean \
      && rm -rf /var/lib/apt/lists/*

RUN apt-get update && apt-get install -y --no-install-recommends \
      libboost-all-dev \
      && apt-get clean \
      && rm -rf /var/lib/apt/lists/*

ENV PATH="/usr/bin/cmake/bin:${PATH}"
