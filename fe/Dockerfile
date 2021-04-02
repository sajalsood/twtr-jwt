FROM node:14.16.0-buster-slim as build

# Specify Args for runtime build
ARG REACT_APP_BE_NETWORK
ARG REACT_APP_BE_PORT

# ENV REACT_APP_BE_NETWORK $REACT_APP_BE_NETWORK
# ENV REACT_APP_BE_PORT $REACT_APP_BE_PORT

WORKDIR /app
COPY . .
RUN npm install
RUN npm run build

# Build to NgInx
FROM nginx
COPY --from=build /app/build /usr/share/nginx/html
