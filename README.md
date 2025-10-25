in this Running-FRPS folder will works 

this is the docker file

in that if we get issu ethan give this perimision  to the folder RUN chmod +x /frps/frps
FROM alpine:latest

# Install bash and any required tools
RUN apk add --no-cache bash

# Set working directory inside the container
WORKDIR /frps

# Copy the entire FRPS directory
COPY FRPS/ .

# Make sure binaries are executable
#RUN chmod +x frps
RUN chmod +x /frps/frps

# Use host network
# CMD will be overridden by docker-compose, or this is the default
CMD ["./frps", "-c", "frps.ini"]
