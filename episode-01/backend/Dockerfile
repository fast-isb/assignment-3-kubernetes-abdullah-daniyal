# Use an official runtime as a parent image
FROM node:20.13.1-alpine3.19

# Set the working directory in the container
WORKDIR /app

# Copy the current directory contents into the container at /usr/src/app
COPY package*.json ./

# Install any needed packages specified in package.json
RUN npm install

# Copy the rest of the application code
COPY . .

# Make port 80 available to the world outside this container
EXPOSE 5000

# Define environment variable, the port and MONGO_DB_SECRET
ENV PORT=5000
# ENV MONGO_DB_SECRET=mongodb://localhost:27017/A3
ENV MONGO_DB_SECRET=mongodb+srv://abdullahdaniyal:superflies1234@cluster0.s5b7diq.mongodb.net/scd3
# Run app.py when the container launches
CMD ["node", "./src/server.js"]