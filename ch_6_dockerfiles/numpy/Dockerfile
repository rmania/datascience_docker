FROM jupyter/base-notebook
USER root
RUN conda install --yes numpy
USER jovyan
# build: docker build -t numpy <given tag> numpy <relatively referenced build context>
# docker run -it numpy ipython <REPL using numpy image>
