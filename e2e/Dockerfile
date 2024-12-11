FROM mcr.microsoft.com/playwright:v1.49.0-noble

RUN corepack enable yarn

WORKDIR /okteto/src

COPY package.json yarn.lock /okteto/src/
RUN yarn install