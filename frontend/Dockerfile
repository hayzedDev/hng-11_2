# Use the latest official Node.js runtime as a parent image
FROM node:latest

# Set the working directory in the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./


# ADD package.json /usr/src/app/package.json

# Copy the rest of the application code to the working directory
COPY . /usr/src/app

# Install any needed packages
RUN npm install



# Expose the port the app runs on
EXPOSE 5173

# Define the command to run the app
CMD [ "npm", "run", "dev", "--", "--host" ]