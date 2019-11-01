# To run the build without the default docker file
docker build -f Dockerfile.dev .
 
# This won't start the server because of missing node_modules folder
docker run -p 3000:3000 -v $(pwd):/app [container-id]

# Fix for above command
docker run -p 3000:3000 -v /app/node_modules -v $(pwd):/app [container-id]

# The docker compose file provided simplifies the above command for running the container.