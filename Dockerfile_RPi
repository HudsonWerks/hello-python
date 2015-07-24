FROM resin/rpi-raspbian:jessie
#FROM resin/beaglebone-black-debian
# Install Python.
RUN apt-get update \
	&& apt-get install -y python \
	# Remove package lists to free up space
	&& rm -rf /var/lib/apt/lists/*

# RUN systemd in container, keeps the container open even if you main process fails. New line from CRAIG @ RESIN.IO
ENV INITSYSTEM on

# copy current directory into /app
COPY . /app

# run python script when container lands on device
CMD ["python", "/app/hello.py"]




Here is an example of a the Dockerfile

FROM resin/raspberrypi2-python

# RUN systemd in container, keeps the container open even if you main process fails.
ENV INITSYSTEM on

# Install deps
RUN apt-get update
RUN apt-get install -y fbi

# install ibm IoT python lib
RUN pip install tweepy

# copy current directory into /app
COPY . /app

# run start script when container starts on device
CMD ["bash", "/app/start.sh"]

