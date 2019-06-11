# Filename: Singularity
Bootstrap: docker
From: continuumio/miniconda3:4.6.14

%labels
   AUTHOR tkolisnik@gmail.com

# This sets global environment variables for anything run within the container
%environment
  export PATH="/opt/conda/bin:/usr/local/bin:/usr/bin:/bin:"
  #unset CONDA_DEFAULT_ENV
  export ANACONDA_HOME=/opt/conda

%post
   export PATH=/opt/conda/bin:$PATH
   echo "Add conda channels."
   conda config --add channels defaults
   conda config --add channels conda-forge
   echo "Install tools."
   conda install --yes pip
   python=3.7.2
   snakemake=5.4.5
#   scikit-learn
#   scipy=1.2.1
   pandas=0.24.2
   numpy=1.16.3
   openssl=1.1.1b
   rpy2=3.0.2
   #scikit-learn
   #conda install --yes scikit-learn
   pip install -U scikit-learn scipy matplotlib
   conda clean --index-cache --tarballs --packages --yes
