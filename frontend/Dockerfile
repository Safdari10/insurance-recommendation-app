# Base stage: Set up the environment
FROM node:20-slim AS base

# Set environment variables for pnpm
ENV PNPM_HOME="/pnpm"
ENV PATH="$PNPM_HOME:$PATH"

# Enable corepack to manage package managers
RUN corepack enable

# Set the working directory
WORKDIR /usr/src/app

# Copy only the lockfile and package.json for better caching
COPY package.json pnpm-lock.yaml ./

# Install dependencies with caching
RUN --mount=type=cache,id=pnpm,target=/pnpm/store pnpm install --frozen-lockfile

# Build stage: Compile the React application
FROM base AS build

# Copy the application code
COPY . .

# Build the application
RUN pnpm run build

# Final stage: Serve the built files using nginx
FROM nginx:alpine

# Copy the built files from the build stage
COPY --from=build /usr/src/app/dist /usr/share/nginx/html

# Copy the nginx configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port 80
EXPOSE 80

# Start nginx
CMD ["nginx", "-g", "daemon off;"]
