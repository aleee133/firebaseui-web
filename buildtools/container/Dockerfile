FROM ubuntu:latest

# Install dependencies: curl, git, jq, python2 and jre8.
RUN apt-get update && \
    apt-get install -y curl git jq python-is-python3 openjdk-11-jre-headless nodejs npm wget

# Print Node version and npm version
RUN node -v
RUN npm -v

# Install hub
RUN curl -fsSL --output hub.tgz https://github.com/github/hub/releases/download/v2.11.2/hub-linux-amd64-2.11.2.tgz
RUN tar --strip-components=2 -C /usr/bin -xf hub.tgz hub-linux-amd64-2.11.2/bin/hub

# Install the lastest Chrome stable version.
# RUN wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
# RUN dpkg -i google-chrome-stable_current_amd64.deb; apt-get -fy install

# Pin Chrome v118 because we're pinning this version in CI.
# TODO: Install the lastest Chrome stable version once we unpin chrome version in CI.
RUN wget http://dl.google.com/linux/chrome/deb/pool/main/g/google-chrome-stable/google-chrome-stable_118.0.5993.70_amd64.deb
RUN dpkg -i google-chrome-stable_118.0.5993.70_amd64.deb; apt-get -fy install
