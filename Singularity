Bootstrap: docker
From: continuumio/miniconda3

%labels
   AUTHOR s.schmeier@protonmail.com

%environment
# ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
# This sets global environment variables for anything run within the container
  export PATH="/opt/conda/bin:$PATH"
  unset CONDA_DEFAULT_ENV
  export ANACONDA_HOME=/opt/conda


%post
   export PATH=/opt/conda/bin:$PATH
   #conda update --yes -q conda 
   echo "We add conda channels."
   conda config --add channels defaults
   conda config --add channels bioconda
   conda config --add channels conda-forge
   conda update -n base -c defaults conda
   echo "We install tools."
   conda install --yes star picard samtools tabix sambamba gatk4 freebayes snpeff snpsift bcftools multiqc
   conda clean --index-cache --tarballs --packages --yes
   conda list > /conda.txt
   touch /`date -u -Iseconds`


# 20190918
# star 2.7.2b
# picard 2.20.8
# samtools 1.9
# tabix 0.2.6
# sambamba 0.7.0
# gatk4 4.1.3
# freebayes 1.3.1
# snpeff 4.3.1
# snpsift 4.3.1
# bcftools 1.9
# multiqc 1.7
