# Step 1: Use an official lightweight Node.js image
FROM node:20-alpine

# Step 2: Set the working directory inside the container
WORKDIR /app

# Step 3: Securely install pnpm globally within the container
RUN npm install -g pnpm

# Step 4: Copy package manifests to install dependencies
COPY package.json pnpm-lock.yaml* ./

# Step 5: Turn off automated script execution for added security
RUN pnpm config set ignore-scripts true

# Step 6: Install the React dependencies
RUN pnpm install

# Step 7: Copy the rest of your frontend source files
COPY . .

# Step 8: Inform Docker that Vite/React defaults to port 5173
EXPOSE 5173

# Step 9: Start the development server with host binding enabled
CMD ["pnpm", "run", "dev", "--", "--host"]