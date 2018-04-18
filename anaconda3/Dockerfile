FROM centos:7

# install precondition packages for anaconda3
RUN yum install -y gcc && \
    yum install -y zlib-devel && \
    yum install -y bzip2 && \
    yum install -y bzip2-devel && \
    yum install -y readline && \
    yum install -y readline-devel && \
    yum install -y sqlite && \
    yum install -y sqlite-devel && \
    yum install -y openssl && \
    yum install -y openssl-devel && \ 
    yum install -y git

# install pyenv
RUN git clone git://github.com/yyuu/pyenv.git ~/.pyenv
ENV HOME /root
ENV PYENV_ROOT $HOME/.pyenv
ENV PATH $PYENV_ROOT/bin:$PATH
RUN eval "$(pyenv init -)"

# install anaconda3
RUN pyenv install anaconda3-5.1.0
RUN pyenv global anaconda3-5.1.0
ENV PATH $PYENV_ROOT/versions/anaconda3-5.1.0/bin/:$PATH
RUN conda update conda

# install and update packages
RUN pip install numpy && \
    pip install scipy && \
    pip install pandas && \
    pip install jupyter && \
    pip install scikit-learn && \
    pip install matplotlib
