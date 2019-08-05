#August 5 2019
# Filename: Singularity
Bootstrap: docker
From: continuumio/miniconda3:4.6.14

%labels
   AUTHOR tkolisnik@gmail.com

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
   conda install --yes scikit-learn scipy matplotlib pandas numpy rpy2 libgfortran
   conda update libgfortran --force
   conda clean --index-cache --tarballs --packages --yes
