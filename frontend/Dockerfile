# FROM node:20

# WORKDIR /app

# COPY package*.json ./

# RUN npm install

# COPY . .

# RUN npm run build

# RUN npm install -g serve

# EXPOSE 4000

# CMD ["npm", "run", "dev", "--", "--host", ]
# Step 1: Use an official Node.js runtime as a parent image
FROM node:20

# Step 2: Set the working directory
WORKDIR /app

# Step 3: Copy package.json and package-lock.json (or yarn.lock)
COPY package*.json ./

# Step 4: Install dependencies
RUN npm install

# Step 5: Bundle app source inside Docker image
COPY . .

# Step 6: Build the Vite project
RUN npm run build

# Step 7: Install a server to serve the build, e.g., serve
RUN npm install -g serve

# Step 8: Define environment variables
ENV HOST 0.0.0.0
ENV PORT 4000

# Step 9: Expose the port the app runs on
EXPOSE 4000

# Step 10: Run serve when the container launches
CMD ["serve", "-s", "dist", "-l", "4000"]
