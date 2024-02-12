###################
# BUILD FOR LOCAL DEVELOPMENT
###################

FROM node:20.10.0-bullseye-slim As development


WORKDIR /usr/src/app
ENV NODE_ENV DEVELOPMENT

COPY --chown=node:node package*.json ./
COPY --chown=node:node yarn.lock ./

COPY sources.list /etc/apt/sources.list
RUN apt-get update \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get update \
    && npm config set registry https://npm.partdp.ir/ \
    && yarn

COPY --chown=node:node . .


###################
# BUILD FOR PRODUCTION
###################

FROM node:20.10.0-bullseye-slim As build

WORKDIR /usr/src/app

COPY --chown=backend:backend package*.json ./


COPY --chown=backend:backend --from=development /usr/src/app/node_modules ./node_modules

COPY --chown=backend:backend . .


RUN yarn lint && yarn test --ci && yarn build
USER backend


###################
# PRODUCTION_DEPS
###################
FROM node:20.10.0-bullseye-slim As base_image
ENV NODE_ENV production

WORKDIR /app
COPY --chown=backend:backend --from=development /usr/src/app/node_modules ./node_modules
COPY --chown=backend:backend package.json yarn.lock  ./
COPY sources.list /etc/apt/sources.list
RUN apt-get update \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get update \
    && npm config set registry https://npm.partdp.ir/ 

RUN yarn install --production --ignore-scripts --prefer-offline && yarn cache clean

###################
# PRODUCTION
###################

FROM base_image As production

WORKDIR /app

COPY --chown=backend:backend --from=build /usr/src/app/dist ./dist
COPY --chown=backend:backend ./entrypoint.sh ./

CMD ["bash" ,"entrypoint.sh"]