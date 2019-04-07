To build an image using a custom named file:
"docker build -f Dockerfile.dev ."

To make sure that after building an image and starting a container the changes in the source code will propagate to the image:
"docker run -p 3000:3000 -v /app/node_modules -v \$(pwd):/app <imagename>"
pwd works in Mac and gitbash

If I have a docker-compose.yml I build my image running "docker-compose up"

After having built the image I can manually run the tests inside the container with:
"docker run -it <imageid> npm run test"

to rebuild with docker-compose run: "docker-compose up --build"

Multi-step docker builds

After I create my multistep Dockerfile:
"docker build ."
"docker run -p 8080:80 <image id>>"
