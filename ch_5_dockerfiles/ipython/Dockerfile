FROM miniconda3

LABEL maintainer=@joshuacook
# define ipython iamge consisting of 3 layers
RUN conda update conda && \
    conda install --quiet --yes ipython && \
    conda clean -tipsy
# give image a default runtime command via CMD instruction. Here: execute at runtime
CMD ["ipython"]

