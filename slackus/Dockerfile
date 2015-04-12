# Pull from base Ubuntu image
FROM node:0.12

# Download slackus
RUN git clone https://github.com/jonathanwiesel/slackus.git
RUN cd slackus && npm install

ENV SLACKUS_DISQUS_API_KEY xxx
ENV SLACKUS_DISQUS_API_SECRET xxx
ENV SLACKUS_DISQUS_ACCESS_TOKEN xxx
ENV SLACKUS_DISQUS_FORUM xxx
ENV SLACKUS_SLACK_WEBHOOK xxx

# The command we'll be running when the container starts
CMD node slackus/index.js
