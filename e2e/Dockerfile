FROM mcr.microsoft.com/playwright:v1.55.0-noble

RUN corepack enable yarn

WORKDIR /okteto/src

COPY package.json yarn.lock /okteto/src/
RUN yarn install