FROM alpine:latest

# Add metadata to an image.
# filter: ocker images --filter label=description="crap"
LABEL description="crap"

# Stop immediately if you do a docker stop
STOPSIGNAL SIGKILL

# Run 52 after container starts and then 5s after each prev check completes.
# If a single run takes longer than 3 sec,fail.
# Takes 2 consecutive failures of health check to be considered unhealthy.
# Check if onpe dir exists, otherwise exit.
# Do a docker ps afterwards a few times...
HEALTHCHECK --interval=5s --timeout=3s --retries=2 CMD cd ./nope || exit 1

# Sets a default command to execute when you run the Docker image. 
# If you specify commands, you will exit from container after it executes.
# CMD echo "Hello from the other side"; echo "Hello?"; ls

# Run command when building container (will not cause exit when run).
RUN ls 

# Create a volume
RUN echo "hello world" > /root/hello.txt
VOLUME /root

# Like CMD but can't be overriden by user. Will cause exit.
# ENTRYPOINT date

# Copy local file into /root
#COPY Dockerfile /root

# Set working directory to /root
WORKDIR /root
COPY Dockerfile .

# ADD is similiar but also:
#   can extract a TAR file from source directly
#   can use a URL instead of a local file directory
ADD https://repo1.maven.org/maven2/org/apache/logging/log4j/log4j/2.14.0/log4j-2.14.0.pom /root/ 

# Set environment var for Docker container.
ENV workdir=/root/
RUN echo "workdir=$workdir"


