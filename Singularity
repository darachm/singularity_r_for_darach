Bootstrap: docker
From: ubuntu:18.04
#Bootstrap: localimage
#From: ../ubuntu-1804-updated_container/ubuntu.simg

%labels
MAINTAINER darachm

%help

    This container is for providing `R` with`tidyverse`, `EBImage`, maybe other packages.
    
%post

    apt-get -y update
#    apt-get -y install gnupg2 software-properties-common

    apt-get -y update
    apt-get -y upgrade
#    apt-get -y install git wget g++ gcc-4.8 
    apt-get -y install libxml2-dev libssl-dev curl libcurl4-openssl-dev r-base r-base-dev

    Rscript -e 'install.packages("tidyverse");'
#    Rscript -e 'install.packages("EBImage");'
#    Rscript -e 'install.packages("BiocManager"); BiocManager::install()'

%test

    Rscript -e 'library(tidyverse);'

