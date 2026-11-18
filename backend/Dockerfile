FROM node:26-alpine  
 # Node 26, Alpine variant
WORKDIR /app      
 # where the app lives inside the container
COPY package.json package-lock.json ./   
 # only the two package files
RUN npm ci --omit=dev       
 # install production deps only, exactly as locked
COPY src ./src              
  # now the source code
ENV NODE_ENV=production
EXPOSE 3000               
 # the port server.js listens on
CMD ["node", "src/server.js"]          
    # run node directly on src/server.js