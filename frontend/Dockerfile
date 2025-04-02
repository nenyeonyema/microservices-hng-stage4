# Step 1: Build the frontend application  
FROM node:14-alpine AS build  
WORKDIR /app  
COPY package*.json ./  
RUN npm install  
COPY . .  
RUN npm run build  

# Step 2: Serve the built application with Nginx  
FROM nginx:alpine  

# Copy the custom Nginx configuration file  
COPY nginx.conf /etc/nginx/conf.d/default.conf  

# Copy built frontend files from the previous stage to the Nginx html directory  
COPY --from=build /app/dist /usr/share/nginx/html  

# Expose port 8080 for Traefik to route traffic to frontend  
EXPOSE 8080  

# Start the Nginx server  
CMD ["nginx", "-g", "daemon off;"]
