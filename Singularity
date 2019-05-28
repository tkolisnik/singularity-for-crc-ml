# Filename: Singularity
Bootstrap: docker
From: continuumio/miniconda3:4.4.10

%labels
   AUTHOR tkolisnik@...

# This sets global environment variables for anything run within the container
%environment
  export PATH="/opt/conda/bin:/usr/local/bin:/usr/bin:/bin:"
  unset CONDA_DEFAULT_ENV
  export ANACONDA_HOME=/opt/conda

%post
   export PATH=/opt/conda/bin:$PATH
   echo "Add conda channels."
   conda config --add channels defaults
   conda config --add channels conda-forge
   echo "Install tools."
   conda install --yes python=3.7.2=haf84260_0 
   python-dateutil=2.8.0=py37_0 
   python-irodsclient=0.7.0=py_0 
   snakemake=5.4.5=0 
   snakemake-minimal=5.4.5=py_0 
   scikit-learn=0.21.1=py37hebd9d1a_0 
   scipy=1.2.1=py37h1a1e112_0 
   pandas=0.24.2=py37h0a44026_0 
   numpy=1.16.3=py37h926163e_0 
   numpy-base=1.16.3=py37ha711998_0 
   openssl=1.1.1b=h1de35cc_1
   yaml=0.1.7=hc338f04_2 
   rpy2=3.0.2
   conda clean --index-cache --tarballs --packages --yes
