#
# Building a Docker Image with
# the Latest Ubuntu Version and
# Basic Python Install
# 
# Python for Algorithmic Trading
# (c) Dr. Yves J. Hilpisch
# The Python Quants GmbH
#

# latest Ubuntu version
FROM ubuntu:latest  

# information about maintainer
MAINTAINER yves

# add the bash script
ADD install.sh /
# change rights for the script
RUN chmod u+x /install.sh
# run the bash script
RUN /install.sh
# add the keys
ADD Key/mycert.pem /root/mycert.pem
ADD Key/mykey.key /root/mykey.key
ADD jupyter_notebook_config.py /root/jupyter_notebook_config.py
# prepend the new path
ENV PATH /root/miniconda3/bin:$PATH

EXPOSE 8888
# execute IPython when container is run
# CMD ["ipython"]
CMD ["jupyter lab"]