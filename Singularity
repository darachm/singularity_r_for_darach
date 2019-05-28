Bootstrap: docker
From: ubuntu:18.04
#Bootstrap: localimage
#From: ../ubuntu-1804-updated_container/ubuntu.simg

%labels
MAINTAINER darachm

%help

    This container is for providing `R` with some packages.
    The idea is to make a general environment, allowing bloat over leaving
    things out. 

    Should have access to R packages of:

        tidyverse
        EBImage
        clusterProfiler
    
%post

    apt-get -y update
    apt-get -y install gnupg2 software-properties-common

    apt-get -y update
    apt-get -y upgrade
    apt-get -y install git wget g++ gcc-4.8 
    apt-get -y install libxml2-dev libssl-dev curl libcurl4-openssl-dev
    apt-get -y install pandoc
    apt-get -y install r-base r-base-dev

    Rscript -e 'source("https://bioconductor.org/biocLite.R");BiocInstaller::biocLite(c("clusterProfiler"))'
    Rscript -e 'install.packages("tidyverse");'
    Rscript -e 'install.packages("EBImage");'

%test

    Rscript -e 'library(tidyverse,clusterProfiler);'
    Rscript -e 'installed.packages();'

