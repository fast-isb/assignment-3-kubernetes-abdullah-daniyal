# Use an official runtime as a parent image
FROM node:16.20.2-alpine3.18 as build

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /usr/src/app
COPY package*.json ./

# Install any needed packages specified in package.json
RUN npm install

# Copy the rest of the application code
COPY . .

# Run app.py when the container launches
RUN npm run build


#-----------------------------------------------------#
# Run the build stage
#-----------------------------------------------------#

# Nginx stage
FROM nginx:1.21.5-alpine

# Copy the build output from the previous build stage
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80 to the outside world
EXPOSE 3000

# Command to run Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]