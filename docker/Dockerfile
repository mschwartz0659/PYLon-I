FROM python:3.7.3
ENV WORKING_DIR /app
WORKDIR ${WORKING_DIR}

#Add current local dir to docker 
ADD . ${WORKING_DIR}

#install pip and quickfix from whl
RUN pip3 install -U pip
#RUN pip3 install quickfix/quickfix-1.15.1-cp37-cp37m-linux_x86_64.whl
RUN pip3 install quickfix/quickfix-1.15.1-cp37-cp37m-linux_aarch64.whl

#Update permissions for start script
RUN chmod 755 ${WORKING_DIR}/initiator/*/start.sh 

# Clean up temporary files (if necessary)
#RUN rm -fr ${WORKING_DIR}/initiator/Logs/*
#RUN rm -fr ${WORKING_DIR}/initiator/Sessions/*
