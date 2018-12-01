# Custom images

Dockerfile

## Commands
Some of the basics commands 
```FROM```
```MAINTAINER```
```RUN```
```COPY```
```ENTRYPOINT```
```WORDIR```
```EXPOSE```
```ENV```
```VOLUME```

## Example

```
# Pull the lastest node image
FROM node:latest

# Define who is the mantainer
MAINTAINER oalberto96

# Define environment variables
ENV NODE_ENV=production
ENV PORT=3000

# Copy our source code
COPY      . /var/wwww
# Set the working directory
WORKDIR   /var/www

# Set the volume
VOLUME ["/var/www"]

# Run node command
RUN       npm install

# Expose internal port
EXPOSE $PORT


ENTRYPOINT ["npm", "start"]

```
## Build the image

`-t` is for tag name of the image
`-f` indicate the dockerfile name file if is diferent than "Dockerfile"

```
docker build -t [username]/node -f Dockerfile
```