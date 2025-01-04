FROM python:3.7.3
ENV WORKING_DIR /app
WORKDIR ${WORKING_DIR}

#COPY extracted tarball from local (DL: https://pypi.org/project/quickfix/#files)
COPY ./quickfix-1.15.1 ${WORKING_DIR}/quickfix-1.15.1

#SWITCH Working Dir and build/install quickfix
WORKDIR ${WORKING_DIR}/quickfix-1.15.1
RUN pip3 install -U pip
RUN pip3 install build
RUN python3 -m build -w
RUN pip3 install dist/*

# Switch back to the main working directory
WORKDIR ${WORKING_DIR}

# Copy the rest of your application's files
ADD . ${WORKING_DIR}

#Update permissions for start script
RUN chmod 755 ${WORKING_DIR}/initiator/start.sh 

# Clean up temporary files (if necessary)
RUN rm -fr ${WORKING_DIR}/initiator/Logs/*
RUN rm -fr ${WORKING_DIR}/initiator/Sessions/*

#EXPOSE 5001