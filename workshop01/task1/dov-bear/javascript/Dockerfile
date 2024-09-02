# ARG is used for building and ENV is used for running
ARG NODE_VERSION=22

FROM node:${NODE_VERSION}

LABEL maintainer=marvin
LABEL build_on="Sept 2 2024"

## How to build
# Create a directory /app and cd /app
WORKDIR /app

# Inside /app
# Copy my src
# Copy from local to container (. is the same file name)
COPY main.js .
COPY package*.json .
# Directory must call the same dir name to move the entire dir inside of just the content itself
COPY public public 
COPY views views

# install node modules (RUN is for building)
RUN npm ci

## How to run
ENV PORT=5000
ENV INSTANCE_NAME=teddy_bear
ENV INSTANCE_HASH=hash

# What are the exposed port
EXPOSE ${PORT}

# Run the application (2 Ways: Entry point and commands)
ENTRYPOINT node main

CMD [ "" ]