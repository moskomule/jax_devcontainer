FROM nvidia/cuda:11.5.1-cudnn8-devel-ubuntu20.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update -qq \
    && apt-get install -y -qq \
    build-essential \
    curl \
    git \
    nvtop \
    locales \
    tmux \
    wget \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && chsh -s /bin/zsh \
    # to display non-ascii correctly
    && locale-gen en_US.UTF-8

ENV CONDADIR /opt/conda
RUN wget -q https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda.sh \
    && chmod +x ~/miniconda.sh \
    && bash ~/miniconda.sh -b -p ${CONDADIR} \
    && rm ~/miniconda.sh \
    && ${CONDADIR}/bin/conda install python=3.9 -y \
    && ${CONDADIR}/bin/conda install -y \
    ipython \
    ipykernel \
    && ${CONDADIR}/bin/conda install -c conda-forge starship \
    && ${CONDADIR}/bin/conda update --all -y \
    && ${CONDADIR}/bin/pip install -U "jax[cuda]" -f https://storage.googleapis.com/jax-releases/jax_releases.html \
    && ${CONDADIR}/bin/pip install -U pip \
    && ${CONDADIR}/bin/pip install -U \
    flax \
    jupyter \
    optax  \
    rich \
    tensorflow \
    tensorflow-datasets\
    glances[gpu] \
    && ${CONDADIR}/bin/conda clean -afy \
    && echo "eval \$(starship init zsh)" >> ${HOME}/.zshrc

ENV XLA_PYTHON_CLIENT_PREALLOCATE=false
ENV PATH=${CONDADIR}/bin:$PATH
