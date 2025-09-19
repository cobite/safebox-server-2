# Use official AntTP image
FROM traktion/anttp:latest

# Install Node.js and npm (if missing)
RUN apk add --no-cache nodejs npm

WORKDIR /app

# Copy only package.json & install
COPY package*.json ./
RUN npm install

# Copy your server code
COPY src ./src
COPY dist ./dist  # if you build locally, or build here

# If you need to build TS
RUN npm run build

EXPOSE 8081

CMD ["npm", "start"]