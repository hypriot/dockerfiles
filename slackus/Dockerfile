# Pull from base Ubuntu image
FROM node:0.12

# Download slackus
RUN git clone https://github.com/jonathanwiesel/slackus.git
RUN cd slackus && npm install

ENV DRONE_GITHUB_CLIENT xxx
ENV DRONE_GITHUB_SECRET xxx

# The command we'll be running when the container starts
CMD node slackus/index.js
